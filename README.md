# [Please](https://please.build) Go rules and definitions

**Note:** This is still very much **experimental**, but [please](https://please.build) looks like a great alternative to [make](https://en.wikipedia.org/wiki/Make_(software)), I love it.

## Usage

Add the following to `BUILD` in your project root:

```starlark
github_repo(
    name = "please-go",
    repo = "sagikazarmark/please-go",
    revision = "master",
)
```


### GolangCI lint

Add the following to your root `.plzconfig` file:

```
[buildconfig]
golangci-lint-tool = ///please-go//third_party:golangci-lint
```

Then run `plz run ///please-go//tools:golangci-lint`.

You can also pin the project to a specific version, which is optional, but strongly recommended:

```
[buildconfig]
; ...
golangci-lint-version = 1.27.0
```

Defining an [alias](https://please.build/config.html) is usually also a good idea:

```
[alias "lint"]
desc = Runs the linters for this repo
cmd = run ///please-go//tools:golangci-lint --
```

Then you can just run the linter by executing `plz lint`. It also passes arguments to the `golangci-lint run` command,
so for example `plz lint -v` will run the linter in verbose mode.

If you already have GolangCI installed somewhere, you can use it by specifying the path to the executable:

```
[buildconfig]
golangci-lint-tool = path/to/golangci-lint
```
