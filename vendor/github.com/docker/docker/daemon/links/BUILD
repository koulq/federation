load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["links.go"],
    importpath = "github.com/docker/docker/daemon/links",
    visibility = ["//visibility:public"],
    deps = ["//vendor/github.com/docker/go-connections/nat:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = ["links_test.go"],
    importpath = "github.com/docker/docker/daemon/links",
    library = ":go_default_library",
    deps = ["//vendor/github.com/docker/go-connections/nat:go_default_library"],
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
