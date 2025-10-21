Fork of https://huggingface.co/apple/coreml-FastViT-T8 to demonstrate an issue in `rules_apple` 4.2.0.

Running `bazel build //...` should output:

```
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/rules_apple+/apple/internal/testing/ios_rules.bzl", line 77, column 60, in _ios_unit_test_bundle_impl
		return apple_test_bundle_support.apple_test_bundle_impl(
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/rules_apple+/apple/internal/testing/apple_test_bundle_support.bzl", line 545, column 41, in _apple_test_bundle_impl
		processor_result = processor.process(
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/rules_apple+/apple/internal/processor.bzl", line 748, column 36, in _process
		partial_outputs = [partial.call(p) for p in partials]
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/bazel_skylib+/lib/partial.bzl", line 43, column 28, in _call
		return partial.function(*function_args, **function_kwargs)
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/rules_apple+/apple/internal/partials/resources.bzl", line 299, column 26, in _resources_partial_impl
		resources.deduplicate(
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/rules_apple+/apple/internal/resources.bzl", line 997, column 42, in _deduplicate
		deduplicated = _deduplicate_field(
	File "/private/var/tmp/_bazel_johnflanagan/a29065da0d532a50315a8974596a3ed4/external/rules_apple+/apple/internal/resources.bzl", line 942, column 49, in _deduplicate_field
		path_origins = processed_origins[short_path]
Error: key "example.resource_bundle-intermediates/Example_Resources.bundle/FastViTT8F16.mlmodelc" not found in dictionary
```