load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "interval_tree.go",
    ],
    importpath = "github.com/coreos/etcd/pkg/adt",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["interval_tree_test.go"],
    importpath = "github.com/coreos/etcd/pkg/adt",
    library = ":go_default_library",
)

go_test(
    name = "go_default_xtest",
    srcs = ["example_test.go"],
    importpath = "github.com/coreos/etcd/pkg/adt_test",
    deps = [":go_default_library"],
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
