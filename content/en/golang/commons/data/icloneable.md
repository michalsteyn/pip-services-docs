---
type: docs
title: "ICloneable"
linkTitle: "ICloneable"
gitUrl: "https://github.com/pip-services3-go/pip-services3-commons-go"
description: > 
    Interface to create objects with binary clones.
---

### Description

The ICloneable interface allows you to create objects with binary clones. 

### Methods

#### clone
Creates a binary clone of this object.

> Clone() interface{}

- **returns**: interface{} - a clone of this object.

### Examples

```go
type MyStruct struct {
	...
}
func (c MyStruct) Clone() interface{} {
	cloneObj := new(MyStruct)
	// Copy every attribute from this to cloneObj here.
	...
	return cloneObj
}
```
