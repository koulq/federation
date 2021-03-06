load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "black_lies.go",
        "cache.go",
        "dnskey.go",
        "dnssec.go",
        "handler.go",
        "responsewriter.go",
        "rrsig.go",
        "setup.go",
    ],
    importpath = "github.com/miekg/coredns/middleware/dnssec",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/hashicorp/golang-lru:go_default_library",
        "//vendor/github.com/mholt/caddy:go_default_library",
        "//vendor/github.com/miekg/coredns/core/dnsserver:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/pkg/response:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/pkg/singleflight:go_default_library",
        "//vendor/github.com/miekg/coredns/request:go_default_library",
        "//vendor/github.com/miekg/dns:go_default_library",
        "//vendor/github.com/prometheus/client_golang/prometheus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "black_lies_test.go",
        "cache_test.go",
        "dnssec_test.go",
        "handler_test.go",
        "setup_test.go",
    ],
    importpath = "github.com/miekg/coredns/middleware/dnssec",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/hashicorp/golang-lru:go_default_library",
        "//vendor/github.com/mholt/caddy:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/file:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/pkg/dnsrecorder:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/test:go_default_library",
        "//vendor/github.com/miekg/coredns/request:go_default_library",
        "//vendor/github.com/miekg/dns:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
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
