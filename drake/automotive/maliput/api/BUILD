# -*- python -*-
# This file contains rules for Bazel; see drake/doc/bazel.rst.

load("//tools:cpplint.bzl", "cpplint")
load("//tools:drake.bzl", "drake_cc_googletest", "drake_cc_library")

package(default_visibility = ["//visibility:public"])

drake_cc_library(
    name = "api",
    srcs = [
        "junction.cc",
        "lane.cc",
        "lane_data.cc",
        "road_geometry.cc",
        "segment.cc",
    ],
    hdrs = [
        "branch_point.h",
        "junction.h",
        "lane.h",
        "lane_data.h",
        "road_geometry.h",
        "segment.h",
    ],
    deps = [
        "//drake/common",
        "//drake/math:geometric_transform",
    ],
)

# === test/ ===
drake_cc_googletest(
    name = "lane_data_test",
    srcs = ["test/lane_data_test.cc"],
    deps = [
        ":api",
        "//drake/common:eigen_matrix_compare",
    ],
)

drake_cc_googletest(
    name = "maliput_test",
    srcs = ["test/maliput_test.cc"],
    deps = [
        ":api",
    ],
)

cpplint()
