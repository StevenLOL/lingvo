package(
    default_visibility = ["//visibility:public"],
)

licenses(["notice"])  # Apache 2.0

py_library(
    name = "input_generator",
    srcs = ["input_generator.py"],
    deps = [
        # Implicit six dependency.
        # Implicit tensorflow dependency.
        "//lingvo/core:base_input_generator",
        "//lingvo/core:base_layer",
        "//lingvo/core:py_utils",
        "//lingvo/core:tokenizers",
        "//lingvo/core/ops:py_x_ops",
    ],
)

py_test(
    name = "input_generator_test",
    srcs = ["input_generator_test.py"],
    deps = [
        ":input_generator",
        # Implicit numpy dependency.
        # Implicit six dependency.
        # Implicit tensorflow dependency.
        "//lingvo/core:py_utils",
        "//lingvo/core:test_helper",
    ],
)

py_library(
    name = "encoder",
    srcs = ["encoder.py"],
    deps = [
        # Implicit six dependency.
        # Implicit tensorflow dependency.
        "//lingvo/core:base_encoder",
        "//lingvo/core:base_layer",
        "//lingvo/core:layers",
        "//lingvo/core:model_helper",
        "//lingvo/core:plot",
        "//lingvo/core:py_utils",
        "//lingvo/core:rnn_cell",
        "//lingvo/core:summary_utils",
    ],
)

py_test(
    name = "encoder_test",
    srcs = ["encoder_test.py"],
    deps = [
        ":encoder",
        # Implicit numpy dependency.
        # Implicit tensorflow dependency.
        "//lingvo/core:py_utils",
        "//lingvo/core:test_utils",
    ],
)

py_library(
    name = "fusion",
    srcs = ["fusion.py"],
    deps = [
        "//lingvo/core:base_layer",
        "//lingvo/core:layers",
        "//lingvo/core:py_utils",
        "//lingvo/tasks/lm:layers",
    ],
)

py_library(
    name = "decoder_utils",
    srcs = ["decoder_utils.py"],
    deps = [
        # Implicit tensorflow dependency.
    ],
)

py_library(
    name = "decoder",
    srcs = [
        "decoder.py",
    ],
    deps = [
        ":decoder_utils",
        ":fusion",
        # Implicit six dependency.
        # Implicit tensorflow dependency.
        "//lingvo/core:attention",
        "//lingvo/core:base_decoder",
        "//lingvo/core:base_layer",
        "//lingvo/core:cluster_factory",
        "//lingvo/core:layers",
        "//lingvo/core:plot",
        "//lingvo/core:py_utils",
        "//lingvo/core:recurrent",
        "//lingvo/core:rnn_cell",
        "//lingvo/core:summary_utils",
        "//lingvo/core/ops:py_x_ops",
    ],
)

py_test(
    name = "decoder_test",
    size = "large",
    srcs = ["decoder_test.py"],
    shard_count = 10,
    deps = [
        ":decoder",
        # Implicit python proto dependency.
        # Implicit numpy dependency.
        # Implicit six dependency.
        # Implicit tensorflow dependency.
        "//lingvo/core:py_utils",
        "//lingvo/core:test_utils",
        "//lingvo/core/ops:hyps_py_pb2",
    ],
)