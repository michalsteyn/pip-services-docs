---
type: docs
title: "MapSchema"
linkTitle: "MapSchema"
gitUrl: "https://github.com/pip-services3-nodex/pip-services3-commons-nodex"
description: >
    Schema to validate maps.
---

**Extends:** [Schema](../schema)

### Description

The MapSchema class provides you with a schema to validate maps

### Constructors
Creates a new instance of validation schema and sets its values.
See [IValidationRule](../ivalidation_rule), [TypeCode](../convert/type_code)

> `public` constructor(keyType?: any, valueType?: any, required?: boolean, rules?: [IValidationRule](../ivalidation_rule)[])

- **keyType**: any - type of map keys. Null means that keys may have any type.
- **valueType**: any - type of map values. Null means that values may have any type.
- **required**: boolean - (optional) true to always require non-null values.
- **rules**: [IValidationRule](../ivalidation_rule)[] - (optional) list with validation rules.



### Instance methods

#### getKeyType
Gets the type of map keys.
Null means that keys may have any type.

> `public` getKeyType(): any

- **returns**: any - type of map keys.

#### getValueType
Gets the type of map values.
Null means that values may have any type.

> `public` getValueType(): any

- **returns**: any - type of map values.

#### performValidation
Validates a given value against the schema and configured validation rules.

> `protected` performValidation(path: string, value: any, results: [ValidationResult](../validation_result)[]): void

- **path**: string - dot notation path to the value.
- **value**: any - value to be validated.
- **results**: [ValidationResult](../validation_result)[] - list with validation results to add new results.

#### setKeyType
Sets the type of map keys.
Null means that keys may have any type.

> `public` setKeyType(value: any): void

- **value**: any - type of map keys.

#### setValueType
Sets the type of map values.
Null means that values may have any type.

> `public` setValueType(value: any): void

- **value**: any - type of map values.

### Examples
```typescript
let schema = new MapSchema(TypeCode.String, TypeCode.Integer);
  
schema.validate({ "key1": "A", "key2": "B" });       // Result: no errors
schema.validate({ "key1": 1, "key2": 2 });           // Result: element type mismatch
schema.validate([ 1, 2, 3 ]);                        // Result: type mismatch

```
