# BUILD

# Allow Bazel to access these files (needed for pip.compile + pip.parse)
exports_files([
    "requirements.in",
    "requirements_lock.txt",
])

load("@rules_python//python:pip.bzl", "compile_pip_requirements")
load("@pip//:requirements.bzl", "all_data_requirements", "all_requirements", "all_whl_requirements", "requirement")

# NOTE: To update the requirements, you need to uncomment the rules_python
# override in the MODULE.bazel.
compile_pip_requirements(
    name = "requirements",
    src = "requirements.in",
    python_version = "3.11",
    requirements_txt = "requirements_lock_3_11.txt",
)

# Your main Python script target
py_binary(
    name = "main",
    srcs = ["main.py"],
    deps = [
        requirement("openai"),
    ],
)
