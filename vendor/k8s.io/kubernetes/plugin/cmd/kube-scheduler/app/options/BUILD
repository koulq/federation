package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = ["options.go"],
    importpath = "k8s.io/kubernetes/plugin/cmd/kube-scheduler/app/options",
    deps = [
        "//vendor/github.com/spf13/pflag:go_default_library",
        "//vendor/k8s.io/apiserver/pkg/util/feature:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/api:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/api/legacyscheme:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/componentconfig:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/componentconfig/install:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/componentconfig/v1alpha1:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/client/leaderelectionconfig:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/features:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubelet/apis:go_default_library",
        "//vendor/k8s.io/kubernetes/plugin/pkg/scheduler/factory:go_default_library",
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
)

go_test(
    name = "go_default_test",
    srcs = ["options_test.go"],
    importpath = "k8s.io/kubernetes/plugin/cmd/kube-scheduler/app/options",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/spf13/pflag:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/diff:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/componentconfig:go_default_library",
    ],
)
