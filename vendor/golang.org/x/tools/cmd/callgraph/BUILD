load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "golang.org/x/tools/cmd/callgraph",
    visibility = ["//visibility:private"],
    deps = [
        "//vendor/golang.org/x/tools/go/buildutil:go_default_library",
        "//vendor/golang.org/x/tools/go/callgraph:go_default_library",
        "//vendor/golang.org/x/tools/go/callgraph/cha:go_default_library",
        "//vendor/golang.org/x/tools/go/callgraph/rta:go_default_library",
        "//vendor/golang.org/x/tools/go/callgraph/static:go_default_library",
        "//vendor/golang.org/x/tools/go/loader:go_default_library",
        "//vendor/golang.org/x/tools/go/pointer:go_default_library",
        "//vendor/golang.org/x/tools/go/ssa:go_default_library",
        "//vendor/golang.org/x/tools/go/ssa/ssautil:go_default_library",
    ],
)

go_binary(
    name = "callgraph",
    importpath = "golang.org/x/tools/cmd/callgraph",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["main_test.go"],
    importpath = "golang.org/x/tools/cmd/callgraph",
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
    srcs = [
        ":package-srcs",
        "//vendor/golang.org/x/tools/cmd/callgraph/testdata/src/pkg:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
