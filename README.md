# minimal-reproduction-template

First, read the [Renovate minimal reproduction instructions](https://github.com/renovatebot/renovate/blob/main/docs/development/minimal-reproductions.md).

Then replace the current `h1` with the Renovate Issue/Discussion number.

## Current behavior

Renovate doesn’t find the dependency on `hedron_compile_commands`.  The debug
logs show something along the lines of

    DEBUG: Matched 1 file(s) for manager bazel-module: MODULE.bazel
    DEBUG: A 'bazel_dep' was not found for 'hedron_compile_commands'.

## Expected behavior

Renovate should find the dependency, even if there’s no `version` attribute in
`bazel_dep`.

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
