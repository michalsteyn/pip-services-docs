
```dart
//skip = 25, take = 50, total = False
var paging = PagingParams(25, 50, false);
var result = await _persistence.getPageByFilter(null, null, paging);

```

