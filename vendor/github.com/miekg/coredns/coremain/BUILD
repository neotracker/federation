load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "run.go",
        "version.go",
    ],
    importpath = "github.com/miekg/coredns/coremain",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/mholt/caddy:go_default_library",
        "//vendor/github.com/miekg/coredns/core:go_default_library",
        "//vendor/github.com/miekg/coredns/core/dnsserver:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["run_test.go"],
    importpath = "github.com/miekg/coredns/coremain",
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
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
