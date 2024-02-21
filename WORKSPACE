load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

##############################################################################
##########################  bazel skylib          ############################
##############################################################################

load("//third_party/bazel_skylib:workspace.bzl", bazel_skylib = "repo")

bazel_skylib()

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

##############################################################################
##########################  rules_cuda           ############################
##############################################################################

load("//third_party/rules_cuda:workspace.bzl", rules_cuda_workspace = "repo")

rules_cuda_workspace()

load("@rules_cuda//cuda:repositories.bzl", "register_detected_cuda_toolchains", "rules_cuda_dependencies")

rules_cuda_dependencies()

register_detected_cuda_toolchains()

##############################################################################
##########################  nlohmann_json         ############################
##############################################################################

git_repository(
    name = "nlohmann_json",
    commit = "0457de21cffb298c22b629e538036bfeb96130b7",
    remote = "https://github.com/nlohmann/json",
)

##############################################################################
##########################  fmt         ############################
##############################################################################

git_repository(
    name = "fmt",
    commit = "0166f455f6681144a18553d2ea0cda8946bff019",
    patch_cmds = [
        "mv support/bazel/.bazelversion .bazelversion",
        "mv support/bazel/BUILD.bazel BUILD.bazel",
        "mv support/bazel/WORKSPACE.bazel WORKSPACE.bazel",
    ],
    remote = "https://github.com/fmtlib/fmt",
)

##############################################################################
##########################  nvbench               ############################
##############################################################################

load("//third_party/nvbench:workspace.bzl", nvbench = "repo")

nvbench()
