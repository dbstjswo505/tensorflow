licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//tensorflow/stream_executor:__subpackages__"])

load("//tensorflow/core:platform/default/build_config_root.bzl", "if_static")

cc_library(
    name = "platform",
    textual_hdrs = [
        "initialize.h",
    ],
    deps = ["//tensorflow/core:lib"],
)

cc_library(
    name = "dso_loader",
    srcs = ["dso_loader.cc"] + if_static(
        ["dlopen_checker_stub.cc"],
        ["dlopen_checker.cc"],
    ),
    hdrs = ["dso_loader.h"],
    deps = [
        "//tensorflow/stream_executor:platform",
        "//tensorflow/stream_executor/lib",
        "//tensorflow/stream_executor/platform",
        "@com_google_absl//absl/strings",
        "@local_config_cuda//cuda:cuda_headers",
    ],
)
