---
type: docs
title: "NullLogger"
linkTitle: "NullLogger"
MethodsgitUrl: "https://github.com/pip-services3-go/pip-services3-components-go"
description: >
    Dummy implementation of logger with no real effect.

---

**Implements:** [ILogger](../ilogger)

### Description

The NullLogger class provides a dummy logger with no real effect.

Important points

- It can be used in testing or in situations when a logger is required but must be disabled.

### Constructors

#### NewNullLogger

> NewNullLogger() [*NullLogger]()

### Methods

#### Level
Gets the maximum log level. Messages with higher log level are filtered out.

> (c [*Logger]()) Level() int

- **returns**: int -  maximum log level.


#### Info
Logs an important information message

> (c [*Logger]()) Info(correlationId string, message string, args ...interface{})

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **message**: string - human-readable message to log.
- **args**: ...interface{} - arguments to parameterize the message.



#### Log
Logs a message at a specified log level.

> (c [*Logger]()) Log(level int, correlationId string, err error, message string, args ...interface{})

- **level**: int - log level.
- **correlationId**: string - (optional) transaction used id to trace execution through the call chain.
- **error**: error - error object associated with this message.
- **message**: string - human-readable message to log.
- **args**: ...interface{} - arguments to parameterize the message.



#### SetLevel
Sets the maximum log level.

> (c [*Logger]()) SetLevel(value int)

- **value**: int - new maximum log level.


#### Trace
Logs a low-level debug information for troubleshooting.

> (c [*Logger]()) Trace(correlationId string, message string, args ...interface{})

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **message**: string - human-readable message to log.
- **args**: ...interface{}- arguments to parameterize the message.


#### Warn
Logs a warning that may or may not have a negative impact.

> (c [*Logger]()) Warn(correlationId string, message string, args ...interface{})

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **message**: string - human-readable message to log.
- **args**: ...interface{} - arguments to parameterize the message.


### See also
- #### [ILogger](../ilogger)
