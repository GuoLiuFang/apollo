load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "behavior_decider",
    hdrs = [
        "behavior_decider.h",
    ],
    srcs = [
        "behavior_decider.cc",
    ],
    deps = [
        "//modules/common/math:box2d",
        "//modules/planning/common/trajectory:discretized_trajectory",
        "//modules/planning/common:frame",
        "//modules/planning/common:planning_gflags",
        "//modules/planning/lattice/behavior_decider:path_time_neighborhood",
        "//modules/planning/lattice/behavior_decider:condition_filter",
        "//modules/planning/proto:lattice_sampling_config_proto",
        "//modules/planning/lattice/behavior_decider:scenario_manager",
        "//modules/planning/reference_line",
        "//modules/planning/proto:planning_proto",
        "//modules/common/proto:pnc_point_proto",
        "//modules/common/proto:common_proto",
        "//external:gflags",
    ],
)

cc_library(
    name = "scenario_manager",
    hdrs = [
        "scenario_manager.h",
    ],
    srcs = [
        "scenario_manager.cc",
    ],
    deps = [
        ":scenarios",
        "//modules/planning/proto:lattice_sampling_config_proto",
        "//modules/planning/common/trajectory:discretized_trajectory",
        "//modules/common/proto:pnc_point_proto",
        "//modules/common/proto:common_proto",
        "//modules/planning/common:frame",
        "//modules/planning/common:reference_line_info",
    ],
)

cc_library(
    name = "scenarios",
    hdrs = [
        "scenario.h",
        "ego_vehicle_scenario.h",
        "signal_light_scenario.h",
    ],
    srcs = [
        "ego_vehicle_scenario.cc",
        "signal_light_scenario.cc",
    ],
    deps = [
        "//modules/planning/proto:lattice_structure_proto",
        "//modules/planning/common/trajectory:discretized_trajectory",
        "//modules/common/proto:pnc_point_proto",
        "//modules/common/proto:common_proto",
        "//modules/planning/common:frame",
        "//modules/planning/common:reference_line_info",
        "//modules/common/adapters:adapter_manager",
        "//modules/common/util:map_util",
        "//modules/perception/proto:perception_proto",
        "//modules/planning/common:planning_gflags",

    ],
)

cc_library(
    name = "feasible_region",
    hdrs = [
        "feasible_region.h",
    ],
    srcs = [
        "feasible_region.cc",
    ],
    deps = [
        "//modules/planning/common:planning_gflags",
        "//modules/common/proto:pnc_point_proto",
    ],
)

cc_library(
    name = "path_time_neighborhood",
    hdrs = [
        "path_time_neighborhood.h",
    ],
    srcs = [
        "path_time_neighborhood.cc",
    ],
    deps = [
        "//modules/common:common",
        "//modules/planning/common:planning_gflags",
        "//modules/planning/reference_line:reference_line",
        "//modules/common/proto:pnc_point_proto",
        "//modules/planning/proto:lattice_structure_proto",
        "//modules/planning/common:frame",
        "//modules/planning/common:obstacle",
        "//modules/planning/lattice/util:reference_line_matcher",
        "//modules/common/math:linear_interpolation",
        "@glog//:glog",
    ],
)

cc_library(
    name = "condition_filter",
    hdrs = [
        "condition_filter.h",
    ],
    srcs = [
        "condition_filter.cc",
    ],
    deps = [
        "//modules/planning/lattice/behavior_decider:path_time_neighborhood",
        "//modules/planning/lattice/behavior_decider:feasible_region",
        "//modules/planning/proto:lattice_structure_proto",
        "//modules/planning/proto:planning_proto",
        "//modules/common/math:linear_interpolation",
    ],
)

cpplint()
