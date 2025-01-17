---
type: docs
title: "MultiString"
linkTitle: "MultiString"
gitUrl: "https://github.com/pip-services3-go/pip-services3-commons-go"
description: > 
    Class used to create objects that contain string translations for multiple languages.
    
---

### Description

The MultiString class allows you to create objects that contain string translations for multiple languages.

Important points

- Language keys use two-letter codes like: *'en', 'sp', 'de', 'ru', 'fr', 'pr'*.
- When a translation for a specific language does not exists, it defaults to English ('en').
- When English does not exists, it falls back to the first defined language



### Examples

```go
values := MultiString.FromTuples(
    "en", "Hello World!",
    "ru", "Привет мир!"
);
value1 := values.Get("ru"); // Result: "Привет мир!"
value2 := values.Get("pt"); // Result: "Hello World!"

```
