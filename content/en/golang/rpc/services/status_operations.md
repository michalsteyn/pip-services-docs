---
type: docs
title: "StatusOperations"
linkTitle: "StatusOperations"
gitUrl: "https://github.com/pip-services3-go/pip-services3-rpc-go"
description: >
    Handles status requests for REST operations.
---

**Implements:** [RestOperations](../rest_operations)

### Description

The StatusOperations class allows you to handle status requests for REST operations.  

### Methods

#### GetStatusOperation
Gets the status of the operation.

> (c [*StatusOperations]()) GetStatusOperation() func(res http.ResponseWriter, req *http.Request)

- **returns**: func(res http.ResponseWriter, req *http.Request) - status operation method


#### SetReferences
Sets references to dependent components.

> (c [*StatusOperations]()) SetReferences(references crefer.IReferences)

- **references**: [IReferences](../../../commons/refer/ireferences) - references to locate the component dependencies.


#### Status
Handles status requests.

> (c *StatusOperations) Status(res http.ResponseWriter, req *http.Request)
- **req**: http.ResponseWriter - an HTTP request
- **res**: *http.Request - an HTTP response
