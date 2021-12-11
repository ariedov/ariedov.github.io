---
title: "Testing Flutter Bloc"
date: 2021-12-11T23:02:30+02:00
draft: false
---

I try to indroduce tests even to my side projects, just because tests fundamentally save time and make you think more about the project architecture.

So of course while using the famous [flutter_bloc](https://pub.dev/packages/flutter_bloc) library for my projects I wanted a nice way to test it. I was very pleasantly surprised when I discovered that the library provides a very nice and elegant way to test the bloc via [bloc_test](https://pub.dev/packages/bloc_test).

First of all, add it to your dev dependencies:
```
dev_dependencies:
  bloc_test: ^9.0.1
```

Then use `blocTest` instead of `test`. The function itself has everything that's required for pleasant testing.

The main ones being:

`build` - is the builder function to actually provide the BLoC.

`act` - add events to the bloc.

`expect` - make sure the bloc emits the right states.

Other helpful functions are also:

`setUp` - nice for initializing your data or mocking.

`verify` - if you want to check not just the states the bloc emits, but also if the flow is right.

A blocTest would like something like this:
```
blocTest<SelectedProficienciesBloc, SelectedProficienciesState>(
  'initial state when loading data',
  build: () => SelectedProficienciesBloc(),
  act: (bloc) => bloc.add(LoadSkills()),
  expect: () => <SelectedProficienciesState>[
    LoadedSelectedProficienciesState(),
  ],
);
```

Happy testing!
