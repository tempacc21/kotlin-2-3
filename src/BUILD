load("@rules_java//java:java_binary.bzl", "java_binary")
load("@rules_kotlin//kotlin:jvm.bzl", "kt_jvm_library")

kt_jvm_library(
    name = "src",
    srcs = ["Demo.kt"],
)

java_binary(
    name = "app",
    main_class = "app.Demo",
    runtime_deps = [":src"],
)
