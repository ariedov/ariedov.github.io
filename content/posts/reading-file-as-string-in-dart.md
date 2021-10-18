---
title: "Reading File as String in Dart"
date: 2021-10-18T17:07:53+03:00
draft: false
---

Reading a file in Dart is very straigthforward, so for this article not to be 4 lines long I have to write something down.
I, personally, needed this for having a json in Unit tests.

```dart
final file = File("path/to/file");
final fileContents = await file.readAsString();
```

Nice reading files in Dart to you =)