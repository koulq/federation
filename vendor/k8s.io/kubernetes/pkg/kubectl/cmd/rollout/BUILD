load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
)

go_library(
    name = "go_default_library",
    srcs = [
        "rollout.go",
        "rollout_history.go",
        "rollout_pause.go",
        "rollout_resume.go",
        "rollout_status.go",
        "rollout_undo.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubectl/cmd/rollout",
    visibility = [
        "//build/visible_to:pkg_kubectl_cmd_rollout_CONSUMERS",
    ],
    deps = [
        "//vendor/github.com/renstrom/dedent:go_default_library",
        "//vendor/github.com/spf13/cobra:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/api/meta:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/types:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/errors:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/watch:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubectl:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubectl/cmd/set:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubectl/cmd/templates:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubectl/cmd/util:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubectl/resource:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/kubectl/util/i18n:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/util/interrupt:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = [
        "//build/visible_to:pkg_kubectl_cmd_rollout_CONSUMERS",
    ],
)
