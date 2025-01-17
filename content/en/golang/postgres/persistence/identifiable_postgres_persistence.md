---
type: docs
title: "IdentifiablePostgresPersistence"
linkTitle: "IdentifiablePostgresPersistence"
gitUrl: "https://github.com/pip-services3-go/pip-services3-postgres-go"
description: >
    Abstract persistence component that stores data in PostgreSQL
    and implements a number of CRUD operations over data items with unique ids.
    
---

**Implements:** [PostgresPersistence](../postgres_persistence)

### Description

The IdentifiablePostgresPersistence class allows you to create persistence components that store data in PostgreSQL databases and implement a number of CRUD operations over data items with unique ids.

Important points

- The data items must implement the [IIdentifiable](../../../commons/data/iidentifiable) interface.
- In basic scenarios child classes shall only override the [GetPageByFilter](../postgres_persistence/#getpagebyfilter), [GetListByFilter](../postgres_persistence/#getlistbyfilter) or [DeleteByFilter](../postgres_persistence/#deletebyfilter) operations with a specific filter function.
- All other operations can be used out of the box. 
- In complex scenarios child classes can implement additional operations by accessing **c.Db** or **c.Collection** properties.

#### Configuration parameters

- **collection**: (optional) Postgres collection name

**connection(s)**:
- **discovery_key**: (optional) key to retrieve the connection from [IDiscovery](../../../components/connect/idiscovery)
- **host**: host name or IP address
- **port**: port number (default: 27017)
- **uri**: resource URI or connection string with all parameters in it

**credential(s)**:
- **store_key**: (optional) key to retrieve the credentials from [ICredentialStore](../../../components/auth/icredential_store)
- **username**: (optional) username
- **password**: (optional) user's password

**options**:
- **connect_timeout**: (optional) number of milliseconds to wait before timing out when connecting a new client (default: 0)
- **idle_timeout**: (optional) number of milliseconds a client must sit idle in the pool and not be checked out (default: 10000)
- **max_pool_size**: (optional) maximum number of clients the pool can contain (default: 10)

#### References
- **\*:logger:\*:\*:1.0** - (optional) [ILogger](../../../components/log/ilogger) components to pass log messages
- **\*:discovery:\*:\*:1.0** - (optional) [IDiscovery](../../../components/connect/idiscovery) services
- **\*:credential-store:\*:\*:1.0** - (optional) credential stores to resolve credentials ([ICredentialStore](../../../components/auth/icredential_store))


### Constructors

#### InheritIdentifiablePostgresPersistence
Creates a new instance of the persistence component.

> InheritIdentifiablePostgresPersistence(overrides IPostgresPersistenceOverrides, proto reflect.Type, tableName string) [*IdentifiablePostgresPersistence]()

- **overrides**: IPostgresPersistenceOverrides - References to override virtual methods.
- **proto**: reflect.Type - TODO: add description. 
- **tableName**: string - (optional) a table name.

### Methods

#### Create
Creates a data item.

> (c *IdentifiablePostgresPersistence) Create(correlationId string, item interface{}) (result interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **item**: interface{} - item to be created.
- **returns**: (result interface{}, err error) - created item


#### DeleteById
Deletes a data item by it's unique id.

> (c *IdentifiablePostgresPersistence) DeleteById(correlationId string, id interface{}) (result interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **id**: interface{} - id of the item to be deleted
- **returns**: (result interface{}, err error) - deleted item


#### DeleteByIds
Deletes multiple data items by their unique ids.

> (c *IdentifiablePostgresPersistence) DeleteByIds(correlationId string, ids []interface{}) error

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **ids**: []interface{} - ids of data items to be deleted.
- **returns**: error - returns error if not received.


#### GetListByIds
Gets a list of data items retrieved by given unique ids.

> (c *IdentifiablePostgresPersistence) GetListByIds(correlationId string, ids []interface{}) (items []interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **ids**: []interface{} - ids of data items to be retrieved
- **returns**: (items []interface{}, err error) - data list


#### GetOneById
Gets a data item by its unique id.

> (c *IdentifiablePostgresPersistence) GetOneById(correlationId string, id interface{}) (item interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **id**: interface{} - id of data item to be retrieved.
- **returns**: (item interface{}, err error)  - data item


#### Set
Sets a data item. If the data item exists it updates it.
Otherwise, it creates a new data item.

> (c *IdentifiablePostgresPersistence) Set(correlationId string, item interface{}) (result interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **item**: interface{} - item to be set.
- **returns**: (result interface{}, err error) - updated item


#### Update
Updates a data item.

> (c *IdentifiablePostgresPersistence) Update(correlationId string, item interface{}) (result interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **item**: interface{} - item to be updated.
- **returns**: (result interface{}, err error) - updated item


#### UpdatePartially
Updates only a few selected fields in a data item.

> (c *IdentifiablePostgresPersistence) UpdatePartially(correlationId string, id interface{}, data [*cdata.AnyValueMap](../../../commons/data/any_value_map)) (result interface{}, err error)

- **correlationId**: string - (optional) transaction id used to trace execution through the call chain.
- **id**: interface{} - id of the data item to be updated.
- **data**: [*cdata.AnyValueMap](../../../commons/data/any_value_map) - map with fields to be updated.
- **returns**: (result interface{}, err error)- updated item

### Examples

```go
TODO: add example

```
