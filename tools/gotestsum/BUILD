CONFIG.setdefault('GOTESTSUM_TOOL', '//third_party/gotestsum')

_gotestsum_tool = check_config(key='GOTESTSUM_TOOL', example='//path/to/gotestsum')

sh_cmd(
    name = 'gotestsum',
    srcs = [_gotestsum_tool],
    cmd = f'exec $(out_location {_gotestsum_tool}) \\\${@}',
    visibility = ["PUBLIC"],
)
