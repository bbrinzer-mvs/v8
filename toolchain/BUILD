package(default_visibility = ["//visibility:public"])

load(":cc_toolchain_config.bzl", "cc_toolchain_config")

# Dummy file group for fields we aren't populating.
filegroup(name = "empty")

#---------------------------------------------------------------------------------------
# Native Toolchains
#---------------------------------------------------------------------------------------

cc_toolchain(
    name = "k8_toolchain",
    toolchain_identifier = "k8-toolchain",
    toolchain_config = ":k8_toolchain_config",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
)
cc_toolchain_config(
    name = "k8_toolchain_config",
    target_cpu = "k8",
    cross = False,
)

cc_toolchain(
    name = "aarch64_toolchain",
    toolchain_identifier = "aarch64-toolchain",
    toolchain_config = ":aarch64_toolchain_config",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
)
cc_toolchain_config(
    name = "aarch64_toolchain_config",
    target_cpu = "aarch64",
    cross = False,
)

cc_toolchain_suite(
    name = "native",
    toolchains = {
        "k8": ":k8_toolchain",
        "aarch64": ":aarch64_toolchain",
    },
)

#---------------------------------------------------------------------------------------
# Cross Toolchains
#---------------------------------------------------------------------------------------

cc_toolchain(
    name = "k8_cross_aarch64_toolchain",
    toolchain_identifier = "k8-cross-aarch64-toolchain",
    toolchain_config = ":k8_cross_aarch64_toolchain_config",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
)
cc_toolchain_config(
    name = "k8_cross_aarch64_toolchain_config",
    target_cpu = "aarch64",
    cross = True,
)

cc_toolchain(
    name = "aarch64_cross_k8_toolchain",
    toolchain_identifier = "aarch64-cross-k8-toolchain",
    toolchain_config = ":aarch64_cross_k8_toolchain_config",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
)
cc_toolchain_config(
    name = "aarch64_cross_k8_toolchain_config",
    target_cpu = "k8",
    cross = True,
)

cc_toolchain_suite(
    name = "cross",
    toolchains = {
        "k8": ":aarch64_cross_k8_toolchain",
        "aarch64": ":k8_cross_aarch64_toolchain",
    },
)
