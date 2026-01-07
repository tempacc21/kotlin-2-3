"""Targets in the repository root"""

load("@gazelle//:def.bzl", "gazelle")
load("@rules_kotlin//kotlin:core.bzl", "define_kt_toolchain", "kt_compiler_plugin", "kt_kotlinc_options")

exports_files(
    [
        "ktlint-baseline.xml",
        ".editorconfig",
    ],
    visibility = ["//:__subpackages__"],
)

# We prefer BUILD instead of BUILD.bazel
# gazelle:build_file_name BUILD
# gazelle:exclude githooks/*
gazelle(
    name = "gazelle",
    env = {
        "ENABLE_LANGUAGES": ",".join([
            "starlark",
            "proto",
            "kotlin",
        ]),
    },
    gazelle = "@multitool//tools/gazelle",
)

kt_kotlinc_options(
    name = "kotlin_compiler_options",
    warn = "error",
    x_annotation_default_target = "first-only",
)

define_kt_toolchain(
    name = "kotlin_toolchain",
    api_version = "2.3",
    experimental_use_abi_jars = True,
    jvm_target = "21",
    kotlinc_options = ":kotlin_compiler_options",
    language_version = "2.3",
)
