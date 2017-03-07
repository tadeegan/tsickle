load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "io_bazel_rules_typescript",
    remote = "sso://bazel/rules_typescript",
    # Use floating HEAD for convenience during development.
    # Don't do this for a real application!
    commit = "master")

load("@io_bazel_rules_typescript//:defs.bzl", "node_repositories", "yarn_install")

# Install a hermetic version of node
# After this is run, a label @io_bazel_typescript_node//:bin/node will exist
node_repositories()

# Install yarn, and run yarn install to create node_modules.
# Also creates the BUILD file under node_modules.
yarn_install(package_json = "//:package.json")
