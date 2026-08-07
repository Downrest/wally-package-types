> # This is a fork to (temporarily) merge the PR for supporting type functions and build the Rust .exe file with the merge.

# Wally Package Types Fixer

A small tool which fixes the issue of [wally](https://github.com/UpliftGames/wally) thunks not including exported types, necessary for proper Luau type checking support.

The tool takes in a path to a Packages folder, as well as a path to a generated sourcemap, and attempts to retrieve the relevant types and append them to the top of the package thunk

Extra note! For Rokit users, use this:
```sh
wally-package-types = "Downrest/wally-package-types@1.6.2"
```

Install your wally packages

```sh
wally install
```

Generate a sourcemap (Rojo 7.1.0+) using

```sh
rojo sourcemap default.project.json --output sourcemap.json
```

then run

```sh
wally-package-types --sourcemap sourcemap.json Packages/
```
