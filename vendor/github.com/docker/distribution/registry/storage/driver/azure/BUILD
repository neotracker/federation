load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["azure.go"],
    importpath = "github.com/docker/distribution/registry/storage/driver/azure",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/Azure/azure-sdk-for-go/storage:go_default_library",
        "//vendor/github.com/docker/distribution/context:go_default_library",
        "//vendor/github.com/docker/distribution/registry/storage/driver:go_default_library",
        "//vendor/github.com/docker/distribution/registry/storage/driver/base:go_default_library",
        "//vendor/github.com/docker/distribution/registry/storage/driver/factory:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["azure_test.go"],
    importpath = "github.com/docker/distribution/registry/storage/driver/azure",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/docker/distribution/registry/storage/driver:go_default_library",
        "//vendor/github.com/docker/distribution/registry/storage/driver/testsuites:go_default_library",
        "//vendor/gopkg.in/check.v1:go_default_library",
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
