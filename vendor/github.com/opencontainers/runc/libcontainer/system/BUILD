load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "proc.go",
        "unsupported.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "linux.go",
            "syscall_linux_64.go",
            "sysconfig.go",
            "xattrs_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "sysconfig_notcgo.go",
        ],
        "//conditions:default": [],
    }),
    cgo = True,
    importpath = "github.com/opencontainers/runc/libcontainer/system",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = ["proc_test.go"],
    importpath = "github.com/opencontainers/runc/libcontainer/system",
    library = ":go_default_library",
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
