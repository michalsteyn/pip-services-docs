---
type: docs
title: "Info"
linkTitle: "Info"
no_list: true
gitUrl: "https://github.com/pip-services3-go/pip-services3-components-go"
description: >
   
    This package contains classes used to create context information objects, 
    which contain information about the context of execution.
    
---
---

**Important information**
- This package is useful for various logging functions where it is necessary to know things like: what source we are logging from, what is 
    the process name, or what the process is/does. 

<div class="module-body"> 

<br>

### Types

#### [ContextInfo](context_info)
Context information component that provides detailed information
about execution context: container or/and process.

Most often ContextInfo is used by logging and performance counters
to identify the source of the collected logs and metrics.


#### [DefaultInfoFactory](default_info_factory)
Creates information components by their descriptors.

</div>
