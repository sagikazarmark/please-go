subinclude("//build_defs/golangci-lint")

CONFIG.setdefault('GOLANGCI_LINT_VERSION', '1.27.0')

golangci_lint_binary(
    name = "golangci-lint",
    version = check_config(key='GOLANGCI_LINT_VERSION', example='1.27.0'),
    visibility = ["PUBLIC"],
)
