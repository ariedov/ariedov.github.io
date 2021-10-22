---
title: "Casting Lists and Maps in Dart"
date: 2021-10-22T19:29:40+03:00
draft: false
---

Another short Dart tip today, and another one that occurred while testing some dart code, but most useful for me when parsing JSON.

### Lists

For `List<dynamic>` I got from a JSON Map, when trying to save them as `List<String>` the errors like:
```
type 'List<dynamic>' is not a subtype of type 'List<String>' 
```

The fix is as simple as using something like that:
```
List<String> correctList = <dynamic>[].cast<String>();
```

### Maps

And for JSON maps that I needed to be parsed as `Map<String, String>`:
```
type '_InternalLinkedHashMap<String, dynamic>' is not a subtype of type 'Map<String, String>?' 
```

Here the fix is very similar to our `List<dynamic>` situation:
```
Map<String, String> correctMap = Map<String, dynamic>().cast<String, String>();
```

Enjoy your collection casting!