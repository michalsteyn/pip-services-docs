
```go

package main

import (
	refer "github.com/pip-services3-go/pip-services3-commons-go/refer"
)

func main() {
	locator1 := refer.NewDescriptor("mygroup", "connector", "aws", "default", "1.0")
	locator2, _ := refer.ParseDescriptorFromString("mygroup:connector:*:*:1.0")
	locator3, _ := refer.ParseDescriptorFromString("mygroup:connector:aws:default:1.0")

	locator1.Match(locator2)      // returns True
	locator1.ExactMatch(locator2) // returns False
	locator1.Equals(locator3)     // returns True
}


```
