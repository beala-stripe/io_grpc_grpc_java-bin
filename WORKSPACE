workspace(name = "java_grpc_bin")

BAZEL_VERSION = "3.6.0"
BAZEL_INSTALLER_VERSION_darwin_SHA = "e20da480e2a41f30ce376418da5aac5ad399755c2fb788d1cce010df896abc16"
BAZEL_INSTALLER_VERSION_linux_SHA = "74818248b8c643da013f3e76c9fdc81c37dd4aceedcc7c55d2ba52ff6044379c"

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

load("//3rdparty:target_file.bzl", "build_external_workspace")
build_external_workspace("third_party_jvm")

load("//3rdparty:workspace.bzl", "maven_dependencies")
maven_dependencies()

