load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["doc.go"],
    importpath = "golang.org/x/crypto/ssh/test",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "dial_unix_test.go",
        "session_test.go",
        "testdata_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "agent_unix_test.go",
            "cert_test.go",
            "forward_unix_test.go",
            "test_unix_test.go",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "agent_unix_test.go",
            "cert_test.go",
            "forward_unix_test.go",
            "test_unix_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "golang.org/x/crypto/ssh/test",
    library = ":go_default_library",
    deps = [
        "//vendor/golang.org/x/crypto/ssh:go_default_library",
        "//vendor/golang.org/x/crypto/ssh/testdata:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "//vendor/golang.org/x/crypto/ssh/agent:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/golang.org/x/crypto/ssh/agent:go_default_library",
        ],
        "//conditions:default": [],
    }),
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
