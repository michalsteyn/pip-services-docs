---
type: docs
title: "AnyValueMap"
linkTitle: "AnyValueMap"
gitUrl: "https://github.com/pip-services3-go/pip-services3-commons-go"
description: > 
    Cross-language implementation of a dynamic map (dictionary) object that can hold values of any type.
    It also provides several methods to convert the stored values to different types.
---

### Description

The AnyValueMap class provides a cross-language implementation of a dynamic map (dictionary) object that can hold values of any type. In addition, it provides several methods to convert the stored values to different types, such as boolean, integer or datetime.

### Constructors

#### NewAnyValueMap
Creates a new instance of the map and assigns its value.

> NewAnyValueMap(value map[string]interface{}) [*AnyValueMap]()

- **values**: map[string]interface{} - (optional) values to initialize this map.

#### InheritAnyValueMap
Creates a new instance of the map and assigns base methods from interface.

> InheritAnyValueMap(base IMap) *AnyValueMap

- **base**: IMap - new map


#### NewEmptyAnyValueMap
Creates a new empty instance of the map.

> NewEmptyAnyValueMap() [*AnyValueMap]()


#### NewAnyValueMapFromMaps
Creates a new AnyValueMap by merging two or more maps.
Maps defined later in the list override values from previously defined maps.

> NewAnyValueMapFromMaps(maps ...map[string]interface{}) [*AnyValueMap](../any_value_map)

- **maps**: ...map[string]interface{} - array of maps to be merged
- **returns**: [*AnyValueMap](../any_value_map) - newly created AnyValueMap.


#### NewAnyValueMapFromTuples
Creates a new AnyValueMap from a list of key-value pairs called tuples.

> NewAnyValueMapFromTuples(tuples ...interface{}) [*AnyValueMap](../any_value_map)

- **tuples**: ...interface{} - list of values where odd elements are keys and the following even elements are values.
- **returns**: [*AnyValueMap](../any_value_map) - newly created AnyValueArray


#### NewAnyValueMapFromTuplesArray
Creates a new AnyValueMap from a list of key-value pairs called tuples.
The method is similar to [NewAnyValueMapFromTuples](#NewAnyValueMapFromTuples) but tuples are passed as array instead of parameters.

> NewAnyValueMapFromTuplesArray(tuples []interface{}) [*AnyValueMap](../any_value_map)

- **tuples**: []interface{} - list of values where odd elements are keys and the following even elements are values
- **returns**: [*AnyValueMap](../any_value_map) - newly created AnyValueArray.


#### NewAnyValueMapFromValue
Converts a specified value into AnyValueMap.

> NewAnyValueMapFromValue(value interface{}) [*AnyValueMap](../any_value_map)

- **value**: interface{} - value to be converted
- **returns**: [*AnyValueMap](../any_value_map) - a newly created AnyValueMap.



### Methods

#### Append
Appends new elements to this map.

> (c [*AnyValueMap]()) Append(value map[string]interface{})

- **map**: map[string]interface{} - map with added elements.


#### Clear
Clears this map by removing all its elements.

> (c [*AnyValueMap]()) Clear()


#### Clone
Creates a binary clone of this object.

> (c [*AnyValueMap]()) Clone() interface{}

- **returns**: interface{} - clone of this object.


#### Get
Gets a map element specified by its key.

> (c [*AnyValueMap]()) Get(key string) interface{}

- **key**: string - key of the element to get.
- **returns**: interface{} - value of the map element.


#### GetAsArray
Converts a map element into an AnyValueArray or returns empty AnyValueArray if the conversion is not possible.  
See [AnyValueArray](../any_value_array), [AnyValueArray.NewAnyValueArrayFromValue](../any_value_array/#newAnyvaluearrayfromvalue)

> (c [*AnyValueMap]()) GetAsArray(key string) [*AnyValueArray](../any_value_array)

- **key**: string - key of element to get.
- **returns**: [*AnyValueArray](../any_value_array) - AnyValueArray value of the element or empty AnyValueArray if the conversion is not supported. 



#### GetAsArrayWithDefault
Converts a map element into an AnyValueArray or returns a default value if the conversion is not possible.  
See [AnyValueArray](../any_value_array)

> (c [*AnyValueMap]()) GetAsArrayWithDefault(key string, defaultValue [*AnyValueArray](../any_value_array)) [*AnyValueArray](../any_value_array)

- **key**: string - key of the element to get.
- **defaultValue**: [*AnyValueArray](../any_value_array) - default value
- **returns**: [*AnyValueArray](../any_value_array) - AnyValueArray value of the element or default value if the conversion is not supported.


#### GetAsBoolean
Converts a map element into a boolean or returns false if the conversion is not possible.

> (c [*AnyValueMap]()) GetAsBoolean(key string) bool

- **key**: string - key of theelement to get.
- **returns**: bool - value of the element or false if the conversion is not supported. 


#### GetAsBooleanWithDefault
Converts a map element into a boolean or returns a default value if the conversion is not possible.  
See [BooleanConverter.ToBooleanWithDefault](../../convert/boolean_converter/#tobooleanwithdefault)

> (c [*AnyValueMap]()) GetAsBooleanWithDefault(key string, defaultValue bool) bool

- **key**: string - key of the element to get.
- **defaultValue**: bool - default value
- **returns**: bool - boolean value of the element or default value if the conversion is not supported. 


#### GetAsDateTime
Converts a map element into a Date or returns the current date if the conversion is not possible.

> (c [*AnyValueMap]()) GetAsDateTime(key string) time.Time

- **key**: string - key of the element to get.
- **returns**: time.Time - Date value of the element or the current date if the conversion is not supported.



#### GetAsDateTimeWithDefault
Converts a map element into a Date or returns a default value if the conversion is not possible.  
See [DateTimeConverter.ToDateTimeWithDefault](../../convert/date_time_converter/#todatetimewithdefault)

> (c [*AnyValueMap]()) GetAsDateTimeWithDefault(key string, defaultValue time.Time) time.Time

- **key**: string - key of element to get.
- **defaultValue**: time.Time - default value
- **returns**: time.Time - Date value of the element or default value if the conversion is not supported. 


#### GetAsDouble
Converts a map element into a double or returns 0 if conversion the is not possible.

> (c [*AnyValueMap]()) GetAsDouble(key string) float64

- **key**: string - key of element to get.
- **returns**: float64 - double value of the element or 0 if the conversion is not supported. 


#### GetAsDoubleWithDefault
Converts a map element into a double or returns a default value if the conversion is not possible.  
See [DoubleConverter.ToDoubleWithDefault](../../convert/double_converter/#todoublewithdefault)

> (c [*AnyValueMap]()) GetAsDoubleWithDefault(key string, defaultValue float64) float64

- **key**: string - key of the element to get.
- **defaultValue**: float64 - default value
- **returns**: float64 - double value of the element or default value if the conversion is not supported. 


#### GetAsFloat
Converts a map element into a float or returns 0 if the conversion is not possible.   

> (c [*AnyValueMap]()) GetAsFloat(key string) float32

- **key**: string - key of the element to get.
- **returns**: float32 - float value of the element or 0 if the conversion is not supported. 


#### GetAsFloatWithDefault
Converts a map element into a flot or returns a default value if the conversion is not possible.  
See [FloatConverter.ToFloatWithDefault](../../convert/float_converter/#tofloatwithdefault)

> (c [*AnyValueMap]()) GetAsFloatWithDefault(key string, defaultValue float32) float32

- **key**: string - key of the element to get.
- **defaultValue**: float32 - default value
- **returns**: float32 - flot value of the element or default value if the conversion is not supported. 


#### GetAsInteger
Converts a map element into an integer or returns 0 if the conversion is not possible.   

> (c [*AnyValueMap]()) GetAsInteger(key string) int

- **key**: string - key of the element to get.
- **returns**: int - integer value of the element or 0 if the conversion is not supported. 



#### GetAsIntegerWithDefault
Converts a map element into an integer or returns a default value if the conversion is not possible.  
See [IntegerConverter.ToIntegerWithDefault](../../convert/integer_converter/#tointegerwithdefault)

> (c [*AnyValueMap]()) GetAsIntegerWithDefault(key string, defaultValue int) int

- **key**: string - key of the element to get.
- **defaultValue**: int - default value
- **returns**: int - integer value of the element or default value if the conversion is not supported.


#### GetAsLong
Converts a map element into a long or returns 0 if the conversion is not possible.  
See [IntegerConverter.ToIntegerWithDefault](../../convert/integer_converter/#tointegerwithdefault)

> (c [*AnyValueMap]()) GetAsLong(key string) int64

- **key**: string - key of the element to get.
- **returns**: int64 - long value of the element or 0 if the conversion is not supported. 



#### GetAsLongWithDefault
Converts a map element into a long or returns a default value if the conversion is not possible.  
See [LongConverter.ToLongWithDefault](../../convert/long_converter/#tolongwithdefault)

> (c [*AnyValueMap]()) GetAsLongWithDefault(key string, defaultValue int64) int64

- **key**: string - key of the element to get.
- **defaultValue**: int64 - default value
- **returns**: int64 - long value of the element or default value if the conversion is not supported.


#### GetAsMap
Converts a map element into an AnyValueMap or returns anempty AnyValueMap if the conversion is not possible.    
See [LongConverter.toLongWithDefault](../../convert/long_converter/#tolongwithdefault)

> (c [*AnyValueMap]()) GetAsMap(key string) [*AnyValueMap](../any_value_map)

- **key**: string - key of the element to get.
- **returns**: [*AnyValueMap](../any_value_map) - AnyValueMap value of the element or empty AnyValueMap if the conversion is not supported. 


#### GetAsMapWithDefault
Converts a map element into an AnyValueMap or returns a default value if the conversion is not possible.

> (c [*AnyValueMap]()) GetAsMapWithDefault(key string, defaultValue [*AnyValueMap](../any_value_map)) [*AnyValueMap](../any_value_map)

- **key**: string - key of the element to get.
- **defaultValue**: [*AnyValueMap](../any_value_map) - default value
- **returns**: [*AnyValueMap](../any_value_map) - AnyValueMap value of the element or default value if the conversion is not supported. 


#### GetAsNullableArray
Converts a map element into an AnyValueArray or returns nil if the conversion is not possible.  
See [AnyValueMap](../any_value_map), [AnyValueMap.NewAnyValueMapFromValue](../any_value_map/#newanyvaluemapfromvalue)

> (c [*AnyValueMap]()) GetAsNullableArray(key string) [*AnyValueMap](../any_value_map)

- **key**: string - key of the element to get.
- **returns**: [*AnyValueMap](../any_value_map) - AnyValueArray value of the element or nil if the conversion is not supported. 


#### GetAsNullableBoolean
Converts a map element into a boolean or returns nil if the conversion is not possible.  
See [BooleanConverter.ToNullableBoolean](../../convert/boolean_converter/#tonullableboolean)

> (c [*AnyValueMap]()) GetAsNullableBoolean(key string) *bool

- **key**: string - key of the element to get.
- **returns**: *bool - boolean value of the element or nil if the conversion is not supported. 


#### GetAsNullableDateTime
Converts a map element into a long or returns default value if the conversion is not possible.  
See [DateTimeConverter.ToNullableDateTime](../../convert/date_time_converter/#tonullabledatetime)

> (c [*AnyValueMap]()) GetAsNullableDateTime(key string) *time.Time

- **key**: string - key of the element to get.
- **returns**: *time.Time - Date value of the element or nil if the conversion is not supported. 


#### GetAsNullableDouble
Converts a map element into a double or returns nil if the conversion is not possible.  
See [DoubleConverter.ToNullableDouble](../../convert/double_converter/#tonullabledouble)

> (c [*AnyValueMap]()) GetAsNullableDouble(key string) *float64

- **key**: string - key of the element to get.
- **returns**: *float64 - double value of the element or nil if conversion is not supported. 


#### GetAsNullableFloat
Converts a map element into a float or returns nil if the conversion is not possible. 
See [FloatConverter.ToNullableFloat](../../convert/float_converter/#tonullablefloat)

> (c [*AnyValueMap]()) GetAsNullableFloat(key string) *float32

- **key**: string - key of the element to get.
- **returns**: *float32 - float value of the element or nil if the conversion is not supported. 


#### GetAsNullableInteger
Converts a map element into an integer or returns nil if the conversion is not possible.  
See [IntegerConverter.ToNullableInteger](../../convert/integer_converter/#tonullableinteger)

> (c [*AnyValueMap]()) GetAsNullableInteger(key string) *int

- **key**: string - key of the element to get.
- **returns**: *int - integer value of the element or nil if the conversion is not supported. 


#### GetAsNullableLong
Converts a map element into a long or returns nil if the conversion is not possible.  
See [LongConverter.ToNullableLong](../../convert/long_converter/#tonullablelong)

> (c [*AnyValueMap]()) GetAsNullableLong(key string) *int64

- **key**: string - key of the element to get.
- **returns**: *int64 - long value of the element or nil if the conversion is not supported. 


#### GetAsNullableMap
Converts a map element into an AnyValueMap or returns nil if the conversion is not possible.  

> (c [*AnyValueMap]()) GetAsNullableMap(key string) [*AnyValueMap](../any_value_map)

- **key**: string - key of the element to get.
- **returns**: [*AnyValueMap](../any_value_map) - AnyValueMap value of the element or nil if the conversion is not supported. 


#### GetAsNullableString
Converts a map element into a string or returns nil if the conversion is not possible.    
See [StringConverter.ToNullableString](../../convert/string_converter/#tonullablestring)

> (c [*AnyValueMap]()) GetAsNullableString(key string) *string

- **key**: string - key of element to get.
- **returns**: *string - string value of the element or nil if the conversion is not supported. 


#### GetAsNullableType
Converts a map element into a value defined by a specified typecode.
If conversion is not possible it returns nil.     
See [TypeConverter.ToNullableType](../../convert/type_converter/#tonullabletype)

> (c [*AnyValueMap]()) GetAsNullableType(typ [convert.TypeCode](../../convert/type_code), key string) interface{}

- **typ**: [convert.TypeCode](../../convert/type_code) - TypeCode that defined the type of the result
- **key**: string - key of the element to get.
- **returns**: interface{} - element value defined by the typecode or nil if the conversion is not supported. 


#### GetAsObject
Gets the value stored in map element without any conversions.
When element key is not defined it returns the entire map value.

> (c [*AnyValueMap]()) GetAsObject(key string) interface{}

- **key**: string - (optional) key of the element to get
- **returns**: interface{} - the element value or value of the map when index is not defined. 


#### GetAsString
Converts a map element into a string or returns *""* if the conversion is not possible.

> (c [*AnyValueMap]()) GetAsString(key string) string

- **key**: string - key of the element to get.
- **returns**: string - string value of the element or *""* if the conversion is not supported. 


#### GetAsStringWithDefault
Converts a map element into a string or returns default value if the conversion is not possible. 
See [StringConverter.ToStringWithDefault](../../convert/string_converter/#tostringwithdefault)

> (c [*AnyValueMap]()) GetAsStringWithDefault(key string, defaultValue string) string

- **key**: string - key of the element to get.
- **defaultValue**: string - default value
- **returns**: string - string value of the element or default value if the conversion is not supported.


#### GetAsType
Converts a map element into a value defined by a specified typecode.
If conversion is not possible it returns a default value for the specified type. 

> (c [*AnyValueMap]()) GetAsType(typ [convert.TypeCode](../../convert/type_code), key string) interface{}

- **type**: [convert.TypeCode](../../convert/type_code) - TypeCode that defined the type of the result
- **key**: string - key of element to get.
- **returns**: interface{} - element value defined by the typecode or default if the conversion is not supported. 


#### GetAsTypeWithDefault
Converts a map element into a value defined by a specified typecode.
If conversion is not possible it returns a default value.    
See [TypeConverter.ToTypeWithDefault](../../convert/type_converter/#totypewithdefault)

> (c [*AnyValueMap]()) GetAsTypeWithDefault(typ [convert.TypeCode](../../convert/type_code), key string, defaultValue interface{}) interface{}

- **typ**: [convert.TypeCode](../../convert/type_code) - TypeCode that defined the type of the result
- **key**: string - key of element to get.
- **defaultValue**: interface{} - default value
- **returns**: interface{} - element value defined by the typecode or default value if the conversion is not supported.



#### GetAsValue
Converts a map element into an AnyValue or returns an empty AnyValue if the conversion is not possible.   
See [AnyValue](../any_value), [AnyValue.constructors](../any_value/#constructors)

> (c [*AnyValueMap]()) GetAsValue(key string) [*AnyValue](../any_value)

- **key**: string - key of element to get.
- **returns**: [*AnyValue](../any_value) - AnyValue value of the element or empty AnyValue if the conversion is not supported. 


#### GetKeys
Gets the keys of all elements stored in this map.

> (c [*AnyValueMap]()) Keys() []string

- **returns**: []string - list with all the map's keys. 


#### InnerValue
Gets the type code for the value stored in this object.

> (c *AnyValue) InnerValue() interface{}

- **returns**: interface{} - type code of the object value.

#### Value
Gets type code for the value stored in this object.

> (c *AnyValue) Value() interface{}

- **returns**: interface{} - type code of the object value.


#### Len
Gets a number of elements stored in this map.

> (c [*AnyValueMap]()) Len() int

- **returns**: int - number of elements in this map.


#### Put
Puts a new value into a map element specified by its key.

> (c [*AnyValueMap]()) Put(key string, value interface{})

- **key**: string - key of the element to put.
- **value**: interface{} - new value for map element.


#### Remove
Removes a map element specified by its key.

> (c [*AnyValueMap]()) Remove(key string)

- **key**: string - key of the element to remove.


#### SetAsObject
Sets a new value to a map element specified by its index.
When the index is not defined, it resets the entire map value.
This method has a double purpose because method overrides are not supported in JavaScript.

> (c [*AnyValueMap]()) SetAsObject(key string, value interface{})

- **key**: string - (optional) key of the element to set
- **value**: interface{} - new element or map value.


#### String
Gets a string representation of the object.
The result is a semicolon-separated list of key-value pairs as
*"key1=value1;key2=value2;key=value3"*

> (c [*AnyValueMap]()) String() string

- **returns**: string - string representation of the object.



### Examples
```go
let value1 = new AnyValueMap({ key1: 1, key2: "123.456", key3: "2018-01-01" });
     
value1.getAsBoolean("key1");   // Result: true
value1.getAsInteger("key2");   // Result: 123
value1.getAsFloat("key2");     // Result: 123.456
value1.getAsDateTime("key3");  // Result: new Date(2018,0,1)

```

### See also
- #### [StringConverter](../../convert/string_converter)
- #### [TypeConverter](../../convert/type_converter)
- #### [StringConverter](../../convert/string_converter)
- #### [BooleanConverter](../../convert/boolean_converter)
- #### [IntegerConverter](../../convert/integer_converter)
- #### [LongConverter](../../convert/long_converter)
- #### [DoubleConverter](../../convert/double_converter)
- #### [FloatConverter](../../convert/float_converter)
- #### [DateTimeConverter](../../convert/date_time_converter)
- #### [ICloneable](../icloneable)
