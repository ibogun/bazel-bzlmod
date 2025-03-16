# Bazel python BUILD setup with bzlmod

Query all targets

```
bazel query "//..."
```

If adding dependencies to `requirements.in` run 

```bash
bazel run //:requirements.update
```

In the build file add  `requirement("openai")`

Example:

```
py_binary(
    name = "main",
    srcs = ["main.py"],
    deps = [
        requirement("openai"),
    ],
)
```

Run main command:

```bash
bazel run :main
```