package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
)

go_binary(
    name = "migratestatus",
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/maintenance/migratestatus",
)

go_library(
    name = "go_default_library",
    srcs = ["migratestatus.go"],
    importpath = "k8s.io/test-infra/maintenance/migratestatus",
    deps = [
        "//maintenance/migratestatus/migrator:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/google/go-github/github:go_default_library",
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
        "//maintenance/migratestatus/migrator:all-srcs",
    ],
    tags = ["automanaged"],
)
