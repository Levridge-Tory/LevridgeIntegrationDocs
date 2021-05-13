hero: EntityMapBuilderExtensions.AddEntityMap Method
# EntityMapBuilderExtensions.AddEntityMap Method
Namespace: Levridge.Integration.IntegrationService.Mapping
Assemblies: Levridge.Integration.IntegrationService.Mapping.dll

Adds an entity to the EntityMap. 

An entity map contains the defintion of the source and target entities to be mapped and the necessary code
to configure the field maps for the entity.

## Overloads

| Overload | Description |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [AddEntityMap<TLeft, TRight>(this IEntityMapBuilder builder, Action<EntityMap<TLeft, TRight>> configure)](AddEntityMap<TLeft,-TRight>(this-IEntityMapBuilder-builder,-Action<EntityMap<TLeft,-TRight>>-configure)) | Maps sourceFieldA to sourceFieldB using the default assignment sourceFieldB = sourceFieldA. |
| [AddEntityMap(this IEntityMapBuilder builder, string entityTypeA, string entityTypeB, Action<EntityMap> configure)](AddEntityMap(this-IEntityMapBuilder-builder,-string-entityTypeA,-string-entityTypeB,-Action<EntityMap>-configure)) | Maps sourceFieldA to sourceFieldB using the transformA2B and transformB2A parameters to provide the transformations. |


### AddEntityMap<TLeft, TRight>(this IEntityMapBuilder builder, Action<EntityMap<TLeft, TRight>> configure)
Adds an Entity Map to the IEntityMapBuilder and provides a configuration action to configure the Entity Mapping.

    public static IEntityMapBuilder AddEntityMap<TLeft, TRight>(this IEntityMapBuilder builder, Action<EntityMap<TLeft, TRight>> configure);

#### Parameters

#### Returns

#### Exceptions

#### Examples


### AddEntityMap(this IEntityMapBuilder builder, string entityTypeA, string entityTypeB, Action<EntityMap> configure)
Adds an Entity Map to the IEntityMapBuilder and provides a configuration action to configure the Entity Mapping.

    public static IEntityMapBuilder AddEntityMap(this IEntityMapBuilder builder, string entityTypeA, string entityTypeB, Action<EntityMap> configure);

#### Parameters

#### Returns

#### Exceptions

#### Examples

