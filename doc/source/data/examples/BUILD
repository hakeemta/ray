load("//bazel:python.bzl", "py_test_run_all_notebooks")

filegroup(
    name = "data_examples",
    srcs = glob(["*.ipynb"]),
    visibility = ["//doc:__subpackages__"]
)

# --------------------------------------------------------------------
# Test all doc/source/data/examples notebooks.
# --------------------------------------------------------------------

# big_data_ingestion.ipynb is not tested right now due to large resource requirements
# and a need of a general overhaul.

py_test_run_all_notebooks(
    size = "medium",
    include = ["*.ipynb"],
    exclude = [
        "big_data_ingestion.ipynb",
        "nyc_taxi_basic_processing.ipynb", # REGRESSION
    ],
    data = ["//doc/source/data/examples:data_examples"],
    tags = ["exclusive", "team:ml"],
    allow_empty = True  # REGRESSION
)
