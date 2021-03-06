load("//tensorflow:tensorflow.bzl", "tf_py_test")  # buildifier: disable=same-origin-load
load("//tensorflow:tensorflow.bzl", "cuda_py_test")  # buildifier: disable=same-origin-load

package(
    default_visibility = ["//tensorflow:internal"],
    licenses = ["notice"],  # Apache 2.0
)

exports_files(["LICENSE"])

tf_py_test(
    name = "assert_cardinality_test",
    srcs = ["assert_cardinality_test.py"],
    deps = [
        "//tensorflow/python/data/experimental/ops:cardinality",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "assert_next_test",
    size = "small",
    srcs = ["assert_next_test.py"],
    tags = [
        "no_oss",
        "no_pip",
        "no_windows",
    ],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

tf_py_test(
    name = "auto_shard_dataset_test",
    size = "medium",
    srcs = ["auto_shard_dataset_test.py"],
    tags = [
        "no_pip",
    ],
    deps = [
        ":reader_dataset_ops_test_base",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/data/experimental/ops:distribute",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/util:nest",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "bucket_by_sequence_length_test",
    size = "medium",
    srcs = ["bucket_by_sequence_length_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python/data/experimental/ops:grouping",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "compression_ops_test",
    srcs = ["compression_ops_test.py"],
    deps = [
        "//tensorflow/python/data/experimental/ops:compression_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

cuda_py_test(
    name = "copy_to_device_test",
    size = "small",
    srcs = ["copy_to_device_test.py"],
    tags = ["no_windows_gpu"],
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python/compat",
        "//tensorflow/python/data/experimental/ops:prefetching_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/ops:iterator_ops",
    ],
)

tf_py_test(
    name = "counter_test",
    size = "small",
    srcs = ["counter_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python/data/experimental/ops:counter",
        "//tensorflow/python/data/kernel_tests:test_base",
    ],
)

tf_py_test(
    name = "csv_dataset_test",
    size = "medium",
    srcs = ["csv_dataset_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python/data/experimental/ops:error_ops",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:readers",
        "//tensorflow/python/eager:context",
    ],
)

py_library(
    name = "data_service_test_base",
    srcs = ["data_service_test_base.py"],
    deps = [
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python/data/experimental/service:server_lib",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

tf_py_test(
    name = "data_service_ops_test",
    size = "medium",
    srcs = ["data_service_ops_test.py"],
    shard_count = 10,
    deps = [
        ":data_service_test_base",
        "//tensorflow:tensorflow_py",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
        "//tensorflow/python/data",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/experimental/service:server_lib",
        "//tensorflow/python/data/kernel_tests:test_base",
    ],
)

tf_py_test(
    name = "data_service_ops_ft_test",
    srcs = ["data_service_ops_ft_test.py"],
    deps = [
        ":data_service_test_base",
        "//tensorflow:tensorflow_py",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
        "//tensorflow/python/data",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/experimental/service:server_lib",
        "//tensorflow/python/data/kernel_tests:test_base",
    ],
)

tf_py_test(
    name = "dense_to_sparse_batch_test",
    srcs = ["dense_to_sparse_batch_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python/data/experimental/ops:batching",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "dense_to_ragged_batch_test",
    srcs = ["dense_to_ragged_batch_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "directed_interleave_dataset_test",
    size = "medium",
    srcs = ["directed_interleave_dataset_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:random_seed",
        "//tensorflow/python/data/experimental/ops:interleave_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "get_single_element_test",
    size = "small",
    srcs = ["get_single_element_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python/data/experimental/ops:get_single_element",
        "//tensorflow/python/data/experimental/ops:grouping",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "group_by_reducer_test",
    size = "medium",
    srcs = ["group_by_reducer_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python/data/experimental/ops:grouping",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "group_by_window_test",
    size = "medium",
    srcs = ["group_by_window_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python/data/experimental/ops:grouping",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "ignore_errors_test",
    srcs = ["ignore_errors_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:io_ops",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:error_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "io_test",
    srcs = ["io_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:io",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

tf_py_test(
    name = "make_batched_features_dataset_test",
    size = "medium",
    srcs = ["make_batched_features_dataset_test.py"],
    tags = ["no_pip"],
    deps = [
        ":reader_dataset_ops_test_base",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:io_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/ops:readers",
        "//tensorflow/python/data/util:nest",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "make_csv_dataset_test",
    size = "medium",
    srcs = ["make_csv_dataset_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/util:nest",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "make_tf_record_dataset_test",
    size = "medium",
    srcs = ["make_tf_record_dataset_test.py"],
    tags = ["no_pip"],
    deps = [
        ":reader_dataset_ops_test_base",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:string_ops",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/util:nest",
    ],
)

tf_py_test(
    name = "map_and_batch_test",
    size = "medium",
    srcs = ["map_and_batch_test.py"],
    tags = [
        "nomsan",  # b/168906619
    ],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:cond_v2",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:script_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python/data/experimental/ops:batching",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "map_defun_op_test",
    size = "small",
    srcs = ["map_defun_op_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:data_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:function",
        "//tensorflow/python:functional_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:session",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python/data/experimental/ops:map_defun",
        "//tensorflow/python/data/kernel_tests:test_base",
    ],
)

tf_py_test(
    name = "matching_files_test",
    size = "small",
    srcs = ["matching_files_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:matching_files",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "model_dataset_test",
    size = "small",
    srcs = ["model_dataset_test.py"],
    tags = [
        "no_oss",
        "no_pip",
        "no_windows",
    ],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "non_serializable_test",
    size = "small",
    srcs = ["non_serializable_test.py"],
    tags = [
        "no_oss",
        "no_pip",
        "no_windows",
    ],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

tf_py_test(
    name = "optimize_dataset_test",
    size = "medium",
    srcs = ["optimize_dataset_test.py"],
    tags = [
        "no_oss",
        "no_pip",
        "no_windows",
    ],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:random_ops",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python/data/experimental/ops:batching",
        "//tensorflow/python/data/experimental/ops:grouping",
        "//tensorflow/python/data/experimental/ops:optimization_options",
        "//tensorflow/python/data/experimental/ops:scan_ops",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/eager:context",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "override_threadpool_test",
    size = "small",
    srcs = ["override_threadpool_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:script_ops",
        "//tensorflow/python/data/experimental/ops:threadpool",
        "//tensorflow/python/data/experimental/ops:unique",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "parallel_interleave_test",
    size = "medium",
    srcs = ["parallel_interleave_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:script_ops",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python/data/experimental/ops:interleave_ops",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "@six_archive//:six",
    ],
)

tf_py_test(
    name = "parse_example_dataset_test",
    size = "medium",
    srcs = ["parse_example_dataset_test.py"],
    shard_count = 4,
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:platform",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python/data/experimental/ops:parsing_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/util:nest",
        "//third_party/py/numpy",
    ],
)

cuda_py_test(
    name = "prefetch_to_device_test",
    size = "small",
    srcs = ["prefetch_to_device_test.py"],
    tags = ["no_windows_gpu"],
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python/data/experimental/ops:prefetching_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

tf_py_test(
    name = "prefetch_with_slack_test",
    size = "small",
    srcs = ["prefetch_with_slack_test.py"],
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/ops:iterator_ops",
        "//tensorflow/python/data/ops:multi_device_iterator_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "random_dataset_test",
    size = "small",
    srcs = ["random_dataset_test.py"],
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/ops:iterator_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

py_library(
    name = "reader_dataset_ops_test_base",
    srcs = [
        "reader_dataset_ops_test_base.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:lib",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:iterator_ops",
        "//tensorflow/python/data/ops:readers",
    ],
)

tf_py_test(
    name = "rebatch_dataset_test",
    size = "small",
    srcs = ["rebatch_dataset_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:image_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/util:nest",
        "//tensorflow/python/ops/ragged:ragged_tensor",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "rejection_resample_test",
    size = "medium",
    srcs = ["rejection_resample_test.py"],
    shard_count = 5,
    tags = [
        "optonly",
    ],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:random_ops",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:resampling",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
        "@six_archive//:six",
    ],
)

tf_py_test(
    name = "replicate_test",
    srcs = ["replicate_test.py"],
    grpc_enabled = True,
    tags = ["no_oss"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_combinations",
        "//tensorflow/python/data/experimental/ops:distribute",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

cuda_py_test(
    name = "scan_test",
    size = "small",
    srcs = ["scan_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:control_flow_v2_toggles",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:script_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:tensor_array_ops",
        "//tensorflow/python:test_ops",
        "//tensorflow/python/data/experimental/ops:scan_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/eager:context",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "shuffle_and_repeat_test",
    size = "medium",
    srcs = ["shuffle_and_repeat_test.py"],
    tags = [
        "no_pip",
        "optonly",
    ],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python/data/experimental/ops:shuffle_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "sleep_test",
    srcs = ["sleep_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:testing",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

py_library(
    name = "sql_dataset_test_base",
    srcs = ["sql_dataset_test_base.py"],
    srcs_version = "PY2AND3",
    visibility = [
        "//tensorflow/python/data/experimental/kernel_tests:__pkg__",
        "//tensorflow/python/data/experimental/kernel_tests/serialization:__pkg__",
    ],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/kernel_tests:test_base",
        "@org_sqlite//:python",
    ],
)

tf_py_test(
    name = "sql_dataset_test",
    size = "medium",
    srcs = ["sql_dataset_test.py"],
    tags = ["no_pip"],
    deps = [
        ":sql_dataset_test_base",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
    ],
)

tf_py_test(
    name = "snapshot_test",
    size = "medium",
    timeout = "long",
    srcs = ["snapshot_test.py"],
    shard_count = 10,
    deps = [
        ":reader_dataset_ops_test_base",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:string_ops",
        "//tensorflow/python/data/experimental/ops:readers",
        "//tensorflow/python/data/experimental/ops:snapshot",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/ops:readers",
        "//tensorflow/python/data/util:nest",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "stats_dataset_ops_test",
    size = "small",
    srcs = ["stats_dataset_ops_test.py"],
    tags = [
        "no_pip",
        "notap",
    ],
    deps = [
        ":reader_dataset_ops_test_base",
        ":stats_dataset_test_base",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python/data/experimental/ops:batching",
        "//tensorflow/python/data/experimental/ops:stats_aggregator",
        "//tensorflow/python/data/experimental/ops:stats_ops",
        "//tensorflow/python/data/experimental/ops:stats_options",
        "//tensorflow/python/data/ops:dataset_ops",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

py_library(
    name = "stats_dataset_test_base",
    srcs = ["stats_dataset_test_base.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/data/kernel_tests:test_base",
    ],
)

tf_py_test(
    name = "take_while_test",
    size = "small",
    srcs = ["take_while_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python/data/experimental/ops:take_while_ops",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/eager:context",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "tf_record_writer_test",
    size = "small",
    srcs = ["tf_record_writer_test.py"],
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:lib",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:writers",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/data/ops:readers",
    ],
)

tf_py_test(
    name = "unique_test",
    size = "small",
    srcs = ["unique_test.py"],
    tags = ["no_pip"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:util",
        "//tensorflow/python/data/experimental/ops:unique",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

tf_py_test(
    name = "variant_test",
    srcs = ["variant_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:util",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)

cuda_py_test(
    name = "wrap_unwrap_test",
    size = "small",
    srcs = ["wrap_unwrap_test.py"],
    deps = [
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/data/kernel_tests:test_base",
        "//tensorflow/python/data/ops:dataset_ops",
    ],
)
