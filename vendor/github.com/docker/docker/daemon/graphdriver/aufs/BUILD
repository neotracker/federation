load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "mount_unsupported.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "aufs.go",
            "dirs.go",
            "mount.go",
            "mount_linux.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/daemon/graphdriver/aufs",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/docker/docker/daemon/graphdriver:go_default_library",
            "//vendor/github.com/docker/docker/pkg/archive:go_default_library",
            "//vendor/github.com/docker/docker/pkg/chrootarchive:go_default_library",
            "//vendor/github.com/docker/docker/pkg/directory:go_default_library",
            "//vendor/github.com/docker/docker/pkg/idtools:go_default_library",
            "//vendor/github.com/docker/docker/pkg/locker:go_default_library",
            "//vendor/github.com/docker/docker/pkg/mount:go_default_library",
            "//vendor/github.com/docker/docker/pkg/system:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/system:go_default_library",
            "//vendor/github.com/opencontainers/selinux/go-selinux/label:go_default_library",
            "//vendor/github.com/pkg/errors:go_default_library",
            "//vendor/github.com/sirupsen/logrus:go_default_library",
            "//vendor/github.com/vbatts/tar-split/tar/storage:go_default_library",
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "aufs_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/daemon/graphdriver/aufs",
    library = ":go_default_library",
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/docker/docker/daemon/graphdriver:go_default_library",
            "//vendor/github.com/docker/docker/pkg/archive:go_default_library",
            "//vendor/github.com/docker/docker/pkg/reexec:go_default_library",
            "//vendor/github.com/docker/docker/pkg/stringid:go_default_library",
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
