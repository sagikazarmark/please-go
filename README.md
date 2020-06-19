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

GolangCI can be executed out of the box using `plz run`:

```bash
plz run ///please-go//tools/golangci-lint
```

Defining an [alias](https://please.build/config.html) makes the command shorter and easier to memorize:

```
[alias "lint"]
desc = Runs the linters for this repo
cmd = run ///please-go//tools/golangci-lint --
```

Then you can just run the linter by executing `plz lint`. It also passes arguments to the `golangci-lint run` command,
so for example `plz lint -v` will run the linter in verbose mode.

The build target installs GolangCI lint by default. You can customize the installation using the following configuration in `.plzconfig`:

```
[buildconfig]
golangci-lint-tool = ///please-go//third_party/golangci-lint
golangci-lint-version = 1.27.0
```

Pinning the linter version is optional, but strongly recommended.
