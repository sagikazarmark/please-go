subinclude("//build_defs/gotestsum")

CONFIG.setdefault('GOTESTSUM_VERSION', '0.5.1')

gotestsum_binary(
    name = "gotestsum",
    version = check_config(key='GOTESTSUM_VERSION', example='0.5.1'),
    visibility = ["PUBLIC"],
)
