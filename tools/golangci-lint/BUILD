CONFIG.setdefault('GOLANGCI_LINT_TOOL', '//third_party/golangci-lint')

_golangci_lint_tool = check_config(key='GOLANGCI_LINT_TOOL', example='//path/to/golangci-lint')

sh_cmd(
    name = 'golangci-lint',
    srcs = [_golangci_lint_tool],
    cmd = f'exec $(out_location {_golangci_lint_tool}) run \\\${@}'
)
