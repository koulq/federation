load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "client.go",
        "service.go",
    ],
    importpath = "github.com/influxdata/influxdb/services/snapshotter",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/influxdata/influxdb:go_default_library",
        "//vendor/github.com/influxdata/influxdb/services/meta:go_default_library",
        "//vendor/github.com/influxdata/influxdb/tcp:go_default_library",
        "//vendor/github.com/influxdata/influxdb/tsdb:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = ["service_test.go"],
    importpath = "github.com/influxdata/influxdb/services/snapshotter_test",
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
