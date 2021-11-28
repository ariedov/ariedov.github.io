---
title: "App Localization on Flutter"
date: 2021-11-28T21:03:20+02:00
draft: false
---

If you are looking for some docs on how to localize your flutter app, the official one is the way to go https://docs.flutter.dev/development/accessibility-and-localization/internationalization. Here I am only noting the steps, so I can recall that for my next app localization attempt with a Flutter app.

So the steps are as follows:

1. Add your flutter localization library in `pubspec.yaml`:
```
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations: # Add this line
    sdk: flutter         # Add this line
  intl: ^0.17.0          # Add this line
```
2. Add `generate: true` flag in `pubspec.yaml`:
```
# The following section is specific to Flutter.
flutter:
  generate: true # Add this line
```
3. Import following in your `main.dart`:
```
import 'package:flutter_localizations/flutter_localizations.dart';
import 'package:flutter_gen/gen_l10n/app_localizations.dart';
```
4. Modify your app as follows:
```
return const MaterialApp(
  title: <Title>,
  localizationsDelegates: [
    AppLocalizations.delegate,
    GlobalMaterialLocalizations.delegate,
    GlobalWidgetsLocalizations.delegate,
    GlobalCupertinoLocalizations.delegate,
  ],
  supportedLocales: [
    Locale('en', ''), // English, no country code
    Locale('ru', ''), // Russian, no country code
  ],
  home: <Home Page>,
);
```
5. Create an `l10n.yaml` file in the project root with the contents being:
```
arb-dir: lib/l10n
template-arb-file: app_en.arb
output-localization-file: app_localizations.dart
```
6. Create the folder for internationalizations: `<project_root>/lib/l10n`, as specified in `l10n.yaml`.
7. Create files for localizations, the template being `app_en.arg`, as specified in `l10n.yaml`. I added `app_ru.arg` specifically.
8. Use your localized strings `Text(AppLocalizations.of(context)!.helloWorld);`

To manually regenerate localized strings from the `*.arb` files, run
```
flutter gen-l10n
```
