---
type: docs
title: "LogTracer"
linkTitle: "LogTracer"
MethodsgitUrl: "https://github.com/pip-services3-go/pip-services3-components-go"
description: >
    Tracer that dumps recorded traces to a logger.
---

### Description

The LogTracer class allows you to create a tracer that dumps recorded traces to a logger.

#### Configuration parameters

**options**:
- **log_level**: log level used to record traces (default: debug)    

#### References

- **\*:logger:\*:\*:1.0** - [ILogger](../../log/ilogger) components to dump the captured counters
- **\*:context-info:\*:\*:1.0** - (optional) [ContextInfo](../../info/context_info) used to detect the context id and specify a counter's source

### Constructors

#### NewLogTracer
Creates a new instance of the tracer.

> NewLogTracer() [*LogTracer]()

### Methods

#### BeginTrace 
Begings recording an operation trace.

> (c [*LogTracer]()) BeginTrace(correlationId string, component string, operation string) [*TraceTiming](../trace_timing)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **component**: string - name of the called component
- **operation**: string - name of the executed operation.
- **return**: [*TraceTiming](../trace_timing) - trace timing object.


#### Configure
Configures component by passing configuration parameters.

> (c [*LogTracer]()) Configure(config [*cconf.ConfigParams](../../../commons/config/config_params)

- **config**: [*cconf.ConfigParams](../../../commons/config/config_params) - configuration parameters to be set.


#### Failure
Records an operation failure with its name, duration and error

> (c [*LogTracer]()) Failure(correlationId string, component string, operation string, err error, duration int64)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **component**: string - name of the called component
- **operation**: string - name of the executed operation.
- **err**: error - error object associated with this trace.
- **duration**: int64 - execution duration in milliseconds.


#### SetReferences
Sets references to dependent components.

> (c [*LogTracer]()) SetReferences(references [cref.IReferences](../../../commons/refer/ireferences))

- **references**: [cref.IReferences](../../../commons/refer/ireferences) - references used to locate the component's dependencies.

#### Trace
Records an operation trace with its name and duration.

> (c [*LogTracer]()) Trace(correlationId string, component string, operation string, duration int64)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **component**: string - name of the called component
- **operation**: string - name of the executed operation.
- **duration**: int64 - execution duration in milliseconds.

### Examples

```go
tracer = NewLogTracer();
tracer.SetReferences(NewReferencesFromTuples(
    NewDescriptor("pip-services", "logger", "console", "default", "1.0"), NewConsoleLogger()
));

timing := trcer.BeginTrace("123", "mycomponent", "mymethod");
...
timing.EndTrace();

if err != nil {
    timing.EndFailure(err);
}
```

### See also
- #### [ITracer](../itracer)
- #### [CachedCounters](../../count/cached_counters)
- #### [CompositeLogger](../../log/composite_logger)
