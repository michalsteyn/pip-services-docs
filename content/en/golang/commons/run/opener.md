---
type: docs
title: "Opener"
linkTitle: "Opener"
gitUrl: "https://github.com/pip-services3-go/pip-services3-commons-go"
description: >
    Helper class that can be used to check whether all components are opened or not, a component is opened or not, and to open one or more components.
---

### Description

The Opener class can be used to check whether all components are opened or not, a component is opened or not, and to open one or more components.

### Methods

#### IsOpen
Checks if all components are opened.

To be checked components must implement the [IOpenable](../iopenable) interface.
If they don't, the call to this method returns true.

> (c *TOpener) IsOpen(components []interface{}) bool

- **components**: []interface{} - list of components that are to be checked.
- **returns**: bool - true if all components are opened and false if at least one component is closed.

#### IsOpenOne
Checks if a specified component is opened.
To be checked components must implement the [IOpenable](../iopenable) interface.
If they don't, the call to this method returns true.

> (c *TOpener) IsOpenOne(component interface{}) bool

- **component**: interface{} - component that is to be checked.
- **returns**: bool - true if component is opened and false otherwise.


#### Open
Opens multiple components.
To be opened components must implement the [IOpenable](../iopenable) interface.
If they don't, the call to this method has no effect.

> (c *TOpener) Open(correlationId string, components []interface{}) error

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **components**: []interface{} - list of components that are to be closed.
- **returns**: error - return error if not opened


#### OpenOne
Opens a specific component.
To be opened components must implement the [IOpenable](../iopenable) interface.
If they don't, the call to this method has no effect.

> (c *TOpener) OpenOne(correlationId string, component interface{}) error

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **component**: interface{} - component that is to be opened.
- **returns**: error - error returned if not opened



### See also
- #### [IOpenable](../iopenable)
