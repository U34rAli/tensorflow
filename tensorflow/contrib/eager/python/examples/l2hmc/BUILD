load("//tensorflow:tensorflow.bzl", "cuda_py_test")

package(
    default_visibility = ["//tensorflow:internal"],
    licenses = ["notice"],  # Apache 2.0
)

py_library(
    name = "neural_nets",
    srcs = ["neural_nets.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/eager/python:tfe",
    ],
)

py_library(
    name = "l2hmc",
    srcs = ["l2hmc.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":neural_nets",
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/eager/python:tfe",
        "//third_party/py/numpy",
    ],
)

cuda_py_test(
    name = "l2hmc_test",
    size = "medium",
    srcs = ["l2hmc_test.py"],
    additional_deps = [
        ":l2hmc",
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/eager/python:tfe",
        "//third_party/py/numpy",
    ],
    shard_count = 4,
    tags = [
        "oss_serial",
    ],
)
