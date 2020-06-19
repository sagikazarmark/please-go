CONFIG.setdefault('MGA_TOOL', '//third_party/mga')

_mga_tool = check_config(key='MGA_TOOL', example='//path/to/mga')

sh_cmd(
    name = 'mga',
    srcs = [_mga_tool],
    cmd = f'exec $(out_location {_mga_tool}) \\\${@}',
    visibility = ["PUBLIC"],
)
