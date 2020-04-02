hero: EntityMap.AddFieldMap Method
# EntityMap.AddFieldMap Method
Namespace: Levridge.Integration.IntegrationService.Mapping
Assemblies: Levridge.Integration.IntegrationService.Mapping.dll

Adds a field map to an EntityMap. 

A field map contains the defintion of the source and target fields to be mapped and any transformation
code necessary to perform the map.

## Overloads

| Overload | Description |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [AddFieldMap&lt;TA, TB&gt;(IEntityField sourceFieldA, IEntityField sourceFieldB)](AddFieldMap&lt;TA,-TB&gt;(IEntityField-sourceFieldA,-IEntityField-sourceFieldB)) | Maps sourceFieldA to sourceFieldB using the default assignment sourceFieldB = sourceFieldA. |
| [AddFieldMap&lt;TA, TB&gt;(IEntityField sourceFieldA, IEntityField sourceFieldB, Func&lt;IEntityField, IEntityField, TB&gt; transformA2B, Func&lt;IEntityField, IEntityField, TA&gt; transformB2A)](AddFieldMap&lt;TA,-TB&gt;(IEntityField-sourceFieldA,-IEntityField-sourceFieldB,-Func&lt;IEntityField,-IEntityField,-TB&gt;-transformA2B,-Func&lt;IEntityField,-IEntityField,-TA&gt;-transformB2A)) | Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations. |
| [AddFieldMap&lt;TA, TB&gt;(IEntityField sourceFieldA, IEntityField sourceFieldB, Func&lt;IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TB&gt; transformA2B, Func&lt;IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TA&gt; transformB2A)](AddFieldMap&lt;TA,-TB&gt;(IEntityField-sourceFieldA,-IEntityField-sourceFieldB,-Func&lt;IEntityField,-IEntityField,-ISourceConfiguration,-ISourceConfiguration,-TB&gt;-transformA2B,-Func&lt;IEntityField,-IEntityField,-ISourceConfiguration,-ISourceConfiguration,-TA&gt;-transformB2A)) | Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations.  transformA2B and transformB2A take ISourceConfiguration parameters to access the source and target data sources. |

---
[AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB)](AddFieldMap<TA,-TB>(IEntityField-sourceFieldA,-IEntityField-sourceFieldB))
Maps sourceFieldA to sourceFieldB using the default assignment sourceFieldB = sourceFieldA.

---
[AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB, Func<IEntityField, IEntityField, TB> transformA2B, Func<IEntityField, IEntityField, TA> transformB2A)](AddFieldMap<TA,-TB>(IEntityField-sourceFieldA,-IEntityField-sourceFieldB,-Func<IEntityField,-IEntityField,-TB>-transformA2B,-Func<IEntityField,-IEntityField,-TA>-transformB2A))
Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations.

---
[AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB, Func<IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TB> transformA2B, Func<IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TA> transformB2A)](AddFieldMap<TA,-TB>(IEntityField-sourceFieldA,-IEntityField-sourceFieldB,-Func<IEntityField,-IEntityField,-ISourceConfiguration,-ISourceConfiguration,-TB>-transformA2B,-Func<IEntityField,-IEntityField,-ISourceConfiguration,-ISourceConfiguration,-TA>-transformB2A))
Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations. 
transformA2B and transformB2A take ISourceConfiguration parameters to access the source and target data sources.

### AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB)
Maps sourceFieldA to sourceFieldB using the default assignment sourceFieldB = sourceFieldA.

        public IFieldMap AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB);

#### Parameters

#### Returns

#### Exceptions

#### Examples


### AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB, Func<IEntityField, IEntityField, TB> transformA2B, Func<IEntityField, IEntityField, TA> transformB2A)
Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations.

        public IFieldMap AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB, Func<IEntityField, IEntityField, TB> transformA2B, Func<IEntityField, IEntityField, TA> transformB2A);

#### Parameters

#### Returns

#### Exceptions

#### Examples


### AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB, Func<IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TB> transformA2B, Func<IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TA> transformB2A)
Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations. 
transformA2B and transformB2A take ISourceConfiguration parameters to access the source and target data sources.

        public IFieldMap AddFieldMap<TA, TB>(IEntityField sourceFieldA, IEntityField sourceFieldB, Func<IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TB> transformA2B, Func<IEntityField, IEntityField, ISourceConfiguration, ISourceConfiguration, TA> transformB2A);

#### Parameters

#### Returns

#### Exceptions

#### Examples
