workspace(
    name = "rules_nodejs_issues",
    managed_directories = {"@npm": ["node_modules"]},
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "c9e59009049fa42198f7087b80398fc4b2698a0f0c7fdde4fb3540c899c9b309",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/1.4.0/rules_nodejs-1.4.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl",
    "node_repositories", "yarn_install")

node_repositories(
    node_version = "10.16.0",
    yarn_version = "1.12.3",
)

yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

load("@npm//:install_bazel_dependencies.bzl", "install_bazel_dependencies")
install_bazel_dependencies()
