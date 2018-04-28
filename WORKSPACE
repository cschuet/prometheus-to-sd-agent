
http_archive(
name = "io_bazel_rules_docker",
sha256 = "3b2c7ece0e89fe7b6456adba1d5aad102ebf735709ca26e5142ce67bfeff4b5d",
strip_prefix = "rules_docker-553d5506bb7325185950f91533b967da8f5bc536",
urls = ["https://github.com/bazelbuild/rules_docker/archive/553d5506bb7325185950f91533b967da8f5bc536.tar.gz"],
)
load(
"@io_bazel_rules_docker//container:container.bzl",
"container_pull",
container_repositories = "repositories",
)
container_repositories()
container_pull(
name = "nginx_base",
registry = "registry.hub.docker.com",
repository = "library/nginx",
)
load(
"@io_bazel_rules_docker//cc:image.bzl",
_cc_image_repos = "repositories",
)
_cc_image_repos()

# Go rules and proto support
http_archive(
name = "io_bazel_rules_go",
sha256 = "bded72dcde6e61aafc18f4d071ca18fadc127627a0676d8cd67de26add6858ec",
strip_prefix = "rules_go-22b1e417e259c7df7b44d728b01d10cbd504fedd",
urls = [
"https://github.com/bazelbuild/rules_go/archive/22b1e417e259c7df7b44d728b01d10cbd504fedd.tar.gz",
],
)
http_archive(
name = "bazel_gazelle",
sha256 = "c1ec72c1a1cb5cd8ee75480d82e316fff4b4e2e7c9bb9ca40fbfd4980b496133",
strip_prefix = "bazel-gazelle-c942db95fcf736f79c95e01cc342c31b260e2a0d",
urls = [
"https://github.com/bazelbuild/bazel-gazelle/archive/c942db95fcf736f79c95e01cc342c31b260e2a0d.tar.gz",
],
)
load("@io_bazel_rules_go//go:def.bzl", "go_register_toolchains",
"go_repository")

go_register_toolchains()

go_repository(
    name = "com_github_googlecloudplatform_k8s_stackdriver",
    importpath = "github.com/cschuet/k8s-stackdriver",
    strip_prefix = "k8s-stackdriver-5c80b9697de59ec1892ce8c91e767738c2018efb",
    urls = ["https://github.com/GoogleCloudPlatform/k8s-stackdriver/archive/5c80b9697de59ec1892ce8c91e767738c2018efb.tar.gz"],
)

load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies")

go_rules_dependencies()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()
