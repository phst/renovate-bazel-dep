# minimal-reproduction-template

First, read the [Renovate minimal reproduction instructions](https://github.com/renovatebot/renovate/blob/main/docs/development/minimal-reproductions.md).

Then replace the current `h1` with the Renovate Issue/Discussion number.

## Current behavior

Mend UI: https://developer.mend.io/github/phst/renovate-bazel-dep

### With `version` attribute in `bazel_dep` absent

Renovate doesn’t find the dependency on `hedron_compile_commands`.  The debug
logs show something along the lines of

    DEBUG: Matched 1 file(s) for manager bazel-module: MODULE.bazel
    DEBUG: A 'bazel_dep' was not found for 'hedron_compile_commands'.

Example logs:
https://developer.mend.io/github/phst/renovate-bazel-dep/-/job/b7aa3542-8332-4a98-b2da-50c6de3871cd

### With `version` attribute in `bazel_dep` present

This works as expected when the `version` attribute in `bazel_dep` is present,
cf. commit 4411ffe5e25fec6b3e8c595b78177c8344f0687d.  In that case Renovate
immediately creates a PR (https://github.com/phst/renovate-bazel-dep/pull/1).

Example logs:
https://developer.mend.io/github/phst/renovate-bazel-dep/-/job/6fa8ceb2-34d5-4f1d-8e5f-883f8c24bc08

## Expected behavior

Renovate should find the dependency, even if there’s no `version` attribute in
`bazel_dep`.  With `git_override`, the version is ignored.  In case of
`hedron_compile_commands`, this means that Renovate doesn’t update the
recommended `MODULE.bazel` snippet
(https://github.com/hedronvision/bazel-compile-commands-extractor/blob/4f28899228fb3ad0126897876f147ca15026151e/README.md#if-you-have-a-modulebazel-file-and-are-using-the-new-bzlmod-system).

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
