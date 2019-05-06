workspace(name = "com_github_johnynek_bazel_deps")

load("@bazel_tools//tools/build_defs/repo:git.bzl",
     "git_repository", "new_git_repository")

git_repository(
    name = "io_bazel_rules_scala",
    remote = "https://github.com/bazelbuild/rules_scala",
    commit = "6c2df00ba0c8c5d1a57547c61e03a90c06e6af9e" # gmishkin portable-classpath
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
scala_repositories()
register_toolchains("//:scala_toolchain")

load("//3rdparty:workspace.bzl", "maven_dependencies")

maven_dependencies()

bind(name = 'io_bazel_rules_scala/dependency/scalatest/scalatest', actual = '//3rdparty/jvm/org/scalatest')
