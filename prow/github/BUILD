package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = [
        "client_test.go",
        "hmac_test.go",
        "links_test.go",
        "types_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/prow/github",
)

go_library(
    name = "go_default_library",
    srcs = [
        "client.go",
        "helpers.go",
        "hmac.go",
        "links.go",
        "types.go",
    ],
    importpath = "k8s.io/test-infra/prow/github",
    deps = [
        "//vendor/github.com/shurcooL/githubql:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/oauth2:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//prow/github/fakegithub:all-srcs",
    ],
    tags = ["automanaged"],
)
