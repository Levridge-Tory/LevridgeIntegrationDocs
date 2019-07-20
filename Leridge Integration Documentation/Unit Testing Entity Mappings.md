# Introduction
This library provides the base classes and utility classes to help you bild unit tests for the integration framework.
It contains classes in the following categories:
* Mapping Unit Test Helper Classes
* Service Bus Helper and Mock classes
* Integration Test Helper Classes

## Mapping Unit Test Helper Classes
### EntityMapBuilderExtensionsTestHelper
The EntityMapBuilderExtensionsTestHelper class contains static methods you can use to obtain an EntityMapProvider<> for a particular scenario
and methods to execute A2B and B2A synchronization using the EntityMapProvider<>
obtained.

To create a unit test that can test a mapping scenario, reference this library
in your test project. Then create a unit test using the following steps:

1. Call GetEntityMapProvider<TSource, TTarget>(Type entityMapBuilderType, string methodName) passing
the source target template parameter types as defined on the mapping method along with the class that contains
the mapping method and the name of the mapping method that you want to test.

    For example, to test the mapping for AxEntities.ScaleTicketGradeFactor and ScaleHouseEntities.ScaleTicketGradeFactor
make the following call: 

    `var mapProvider = EntityMapBuilderExtensionsTestHelper.GetEntityMapProvider<AxEntities.ScaleTicketGradeFactor, ScaleHouseEntities.ScaleTicketGradeFactor>(typeof(AxToScaleEntityMapBuilderExtensions), "MapAXScaleTicketGradeFactor_ScaleHouseScaleTicketGradeFactor");`

2. Instantiate and populate the entities you want to use for mapping. I prefer to use the `[MemberData]` attribute to provide multiple
instances for testing. See [this article](https://andrewlock.net/creating-parameterised-tests-in-xunit-with-inlinedata-classdata-and-memberdata/) for example on providing data for unit tests.
3. Use the EntityMapProvider<> to perform the mapping by calling one of the transform methods on
The EntityMapBuilderExtensionsTestHelper class. For example, to test the B2A mapping for the previous example use the following code:

    `AXentity = EntityMapBuilderExtensionsTestHelper.TransformB2A(mapProvider, ScaleEntity, AXentity);`

4. Assert - check the mapped values

    In order to test the expected values you should have an instance of the target object
with the expected values and then get the transformed object from the target entity and compare
the two. You can pass in an object with the expected values using the MemberData method.

    Example:
```C#
    // Get target object
    var targetObject = AXentity.GetEntityAsDotNetType<AxEntities.ScaleTicketGradeFactor>();

    // Assert
    Assert.NotNull(targetObject);
    Assert.Equal(expectedResult.GradeFactorId, targetObject.GradeFactorId);
    Assert.Equal(expectedResult.GradeFactorValue, targetObject.GradeFactorValue);
    Assert.Equal(expectedResult.TicketNumber, targetObject.TicketNumber);
    Assert.Equal(expectedResult.LineNumber, targetObject.LineNumber);
```
### Using MemberData to Provide Unit Test Data
If you want to use the MemberData method for building data to use in your unit tests
(you can refer to [this article](https://andrewlock.net/creating-parameterised-tests-in-xunit-with-inlinedata-classdata-and-memberdata/) for an over view) here are some ideas.

#### 1. Create Methods to Instantiate and Populate the Source and Expected Target Objects
I would recommend creating a private static method on your test class that recieves parameters that can be used
to initialize the class with the desired values. If you need several parameters you can put them in an object array 
or Key Value pair or even a dictionary.

Example:
```C#
        private static AxEntities.ScaleTicketGradeFactor GetAxTicketGradeFactorObject(int line, string id, string value, string ticketNumber)
        {
            return new AxEntities.ScaleTicketGradeFactor()
            {
                LineNumber = line,
                GradeFactorId = id,
                GradeFactorValue = decimal.Parse(value),
                TicketNumber = ticketNumber
            };
        }
```
#### 2. Create Methods to Instantiate and Populate the Source and Target Entities
Once you have a populated source object you can use it to instantiate and initialize a source Entity.

Example:
```C#
        private static Entity GetAxTicketGradeFactorEntity(AxEntities.ScaleTicketGradeFactor scaleTicketGradeFactor = null)
        {
            var axScaleTicketGradeFactor = scaleTicketGradeFactor ?? new AxEntities.ScaleTicketGradeFactor();
            Entity entity = DynamicsAxEntities.Instance.GetScaleTicketGradeFactorEntity();
            entity.CreateAndPopulateEntityFields(typeof(JSONField<>), axScaleTicketGradeFactor);
            return entity;
        }
```
As you can see, if an object is provided, it is used to initialize the Entity. Otherwise a default object is used.

#### 3. Implement the MemberData Method
As described in [this article](https://andrewlock.net/creating-parameterised-tests-in-xunit-with-inlinedata-classdata-and-memberdata/) for an over view) the MemberData
method must return `IEnumerable<object[]>`. You can craete a method that uses the methods described in the previous steps
to create source & target entities along with a target expected object. Then you can define that method using the `[MemberData]` attribute.

Here is an example MemberData method:
```C#
        public static IEnumerable<object[]> GetSynchronizeA2BGradeFactorData()
        {
            return new List<object[]>
            {
                new object[]
                {
                    GetAxTicketGradeFactorEntity(GetAxTicketGradeFactorObject(1, "A", "8", "0000169")),
                    GetScaleHouseGradeFactorEntity(),
                    GetScaleHouseTicketGradeFactorObject(1, "A", "8", "0000169")
                },
                new object[]
                {
                    GetAxTicketGradeFactorEntity(GetAxTicketGradeFactorObject(2, "AB", "0.3", "0000169")),
                    GetScaleHouseGradeFactorEntity(),
                    GetScaleHouseTicketGradeFactorObject(2, "AB", "0.3", "0000169")
                },
                new object[]
                {
                    GetAxTicketGradeFactorEntity(GetAxTicketGradeFactorObject(3, "AS", "31.3", "0000169")),
                    GetScaleHouseGradeFactorEntity(),
                    GetScaleHouseTicketGradeFactorObject(3, "AS", "31.3", "0000169")
                }
            };
        }
```
### Example Unit Test
Here is an example unit test that tests Ticket Grade Factor entities from the ScaleHouse application to F&O.

```C#
        [Theory]
        [MemberData(nameof(GetSynchronizeB2AGradeFactorData))]
        public void MapScaleTicketGradeFactor_SynchronizeB2AGradeFactor_CorrectMapping(
            Entity AXentity, // AX ticket grade factor
            Entity ScaleEntity, // Scale house ticket grade factor
            AxEntities.ScaleTicketGradeFactor expectedResult)
        {
            // Arrange
            var mapProvider = EntityMapBuilderExtensionsTestHelper.GetEntityMapProvider<AxEntities.ScaleTicketGradeFactor, ScaleHouseEntities.ScaleTicketGradeFactor>
                (typeof(AxToScaleEntityMapBuilderExtensions), "MapAXScaleTicketGradeFactor_ScaleHouseScaleTicketGradeFactor");

            //Act

            // Transform
            AXentity = EntityMapBuilderExtensionsTestHelper.TransformB2A(mapProvider, ScaleEntity, AXentity);

            // Get target object
            var targetObject = AXentity.GetEntityAsDotNetType<AxEntities.ScaleTicketGradeFactor>();

            // Assert
            Assert.NotNull(targetObject);
            Assert.Equal(expectedResult.GradeFactorId, targetObject.GradeFactorId);
            Assert.Equal(expectedResult.GradeFactorValue, targetObject.GradeFactorValue);
            Assert.Equal(expectedResult.TicketNumber, targetObject.TicketNumber);
            Assert.Equal(expectedResult.LineNumber, targetObject.LineNumber);

        }


```



