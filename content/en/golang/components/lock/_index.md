---
type: docs
title: "Lock"
linkTitle: "Lock"
no_list: true
gitUrl: "https://github.com/pip-services3-go/pip-services3-components-go"
description: >
    This package provides a set of interfaces and classes used to create several types of locks.
---
---

<div class="module-body"> 

### Interfaces

#### [ILock](ilock)
Interface for locks to synchronize work or parallel processes and to prevent collisions.
The lock allows to manage multiple locks identified by unique keys.

<br>

### Types

#### [DefaultLockFactory](default_lock_factory)
Creates [ILock](ilock) components by their descriptors.


#### [Lock](lock)
Abstract lock that implements default lock acquisition routine.

#### [MemoryLock](memory_lock)
Lock that is used to synchronize execution within one process using shared memory.
This implementation is not suitable for synchronization of distributed processes.

#### [NullLock](null_lock)
Dummy lock implementation that doesn't do anything.

It can be used in testing or in situations when lock is required
but shall be disabled.

</div>
