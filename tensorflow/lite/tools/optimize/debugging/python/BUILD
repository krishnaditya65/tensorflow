# QuantizationDebugger for TFLite accuracy tooling.
load("//tensorflow:tensorflow.bzl", "pytype_strict_library")
load("//tensorflow:tensorflow.bzl", "py_strict_test")

package(
    default_visibility = [
        "//tensorflow:internal",
    ],
    licenses = ["notice"],
)

pytype_strict_library(
    name = "debugger",
    srcs = ["debugger.py"],
    srcs_version = "PY3",
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow:tensorflow_py",
        "//tensorflow/lite/python:convert",
        "//tensorflow/lite/python:metrics",
        "//tensorflow/python/util:tf_export",
        "//third_party/py/numpy",
    ],
)

py_strict_test(
    name = "debugger_test",
    srcs = [
        "debugger_test.py",
    ],
    python_version = "PY3",
    deps = [
        ":debugger",
        "//tensorflow:tensorflow_py",
        "//tensorflow/lite/python:convert",
        "//tensorflow/lite/python:lite",
        "//tensorflow/lite/python:metrics",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python/platform:client_testlib",
        "//tensorflow/python/training/tracking",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)
