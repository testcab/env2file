env2file
========

A vanilla shell script that outputs the content of `$ENV2FILE_CONTENT` variable to the file specified in `$ENV2FILE_TO`.

If both `$ENV2FILE_CONTENT` and `$ENV2FILE_TO` are empty, nothing will be done.

Use arg `-v` or `--verbose`, or environment variable `ENV2FILE_VERBOSE=1` to show logs of `env2file`.

Note that `$ENV2FILE_CONTENT` can be unset or empty to write an empty file.
