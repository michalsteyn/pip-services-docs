---
type: docs
title: "DataDogLogClient"
linkTitle: "DataDogLogClient"
gitUrl: "https://github.com/pip-services3-go/pip-services3-datadog-go"
description: >
    REST client for DataDog logs.


---

**Implements:** [RestClient](../../../rpc/clients/rest_client)

### Description

The DataDogLogClient class allows you to create a REST client for DataDog logs. 



### Constructors

Creates a new instance of this class.

> NewDataDogLogClient(config [*ConfigParams](../../../commons/config/config_params)) [*DataDogLogClient]()

- **config**: [*ConfigParams](../../../commons/config/config_params) - configuration parameters.


### Methods

#### Configure
Configures a component by passing its configuration parameters.

> (c [*DataDogLogClient]()) Configure(config [*ConfigParams](../../../commons/config/config_params))

- **config**: [*ConfigParams](../../../commons/config/config_params) - configuration parameters to be set.

#### Open
Opens the component.

> (c [*DataDogLogClient]()) Open(correlationId string) error

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **returns**: error - error or nil if no errors occurred.

#### SendLogs
Sends log messages.

> (c [*DataDogLogClient]()) SendLogs(correlationId string, messages [[]DataDogLogMessage](../datadog_log_message)) error

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **messages**: [[]DataDogLogMessage](../datadog_log_message) - messages to send.
- **returns**: error - error or nil if no errors occurred.

#### SetReferences
Sets references to dependent components.

> (c [*DataDogLogClient]()) SetReferences(refs [IReferences](../../../commons/refer/ireferences))

- **references**: [IReferences](../../../commons/refer/ireferences) - references to locate the component's dependencies.
