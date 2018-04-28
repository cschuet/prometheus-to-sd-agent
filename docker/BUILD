package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_docker//container:image.bzl", "container_image")

container_image(
    name = "prometheus-to-sd-agent",
    base = "@cc_image_base//image",
    entrypoint = ["/prometheus-to-sd"],
    files = ["@com_github_googlecloudplatform_k8s_stackdriver//prometheus-to-sd"],
)

