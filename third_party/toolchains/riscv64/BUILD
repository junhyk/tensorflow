load(":cc_config.bzl", "cc_toolchain_config")

package(default_visibility = ["//visibility:public"])

licenses(["restricted"])  # GPLv3

cc_toolchain_suite(
    name = "toolchain",
    toolchains = {
        "riscv64": ":cc-compiler-riscv",
    },
)

filegroup(
    name = "empty",
    srcs = [],
)

filegroup(
    name = "riscv_toolchain_all_files",
    srcs = [
        ":compiler_pieces",
    ],
)

cc_toolchain_config(
    name = "riscv_toolchain_config",
    cpu = "riscv64",
)

cc_toolchain(
    name = "cc-compiler-riscv",
    all_files = ":riscv_toolchain_all_files",
    compiler_files = ":riscv_toolchain_all_files",
    dwp_files = ":empty",
    linker_files = ":riscv_toolchain_all_files",
    objcopy_files = "riscv_toolchain_all_files",
    strip_files = "riscv_toolchain_all_files",
    supports_param_files = 1,
    toolchain_config = ":riscv_toolchain_config",
)

# from riscv-linux-toolchain.BUILD
# package(default_visibility = ["//visibility:public"])

filegroup(
    name = "gcc",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-gcc",
    ],
)

filegroup(
    name = "ar",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-ar",
    ],
)

filegroup(
    name = "ld",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-ld",
    ],
)

filegroup(
    name = "nm",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-nm",
    ],
)

filegroup(
    name = "objcopy",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-objcopy",
    ],
)

filegroup(
    name = "objdump",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-objdump",
    ],
)

filegroup(
    name = "strip",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-strip",
    ],
)

filegroup(
    name = "as",
    srcs = [
        "bin/riscv64-unknown-linux-gnu-as",
    ],
)

filegroup(
    name = "compiler_pieces",
    srcs = glob([
        "riscv64-unknown-linux-gnu/**",
        "lib/gcc/riscv64-unknown-linux-gnu/9.2.0/**",
        "sysroot/usr/**"
    ]),
)
