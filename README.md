env2file
========

A vanilla shell script that outputs the content of `$ENV2FILE_CONTENT` variable to the file specified in `$ENV2FILE_TO`.

If both `$ENV2FILE_CONTENT` and `$ENV2FILE_TO` are empty, nothing will be done.

Use arg `-v` or `--verbose`, or environment variable `ENV2FILE_VERBOSE=1` to show logs of `env2file`.

Use arg `-n` or `--no-clobber`, or environment variable `ENV2FILE_NOCLOBBER=1` to not overwrite an existing file.

Note that `$ENV2FILE_CONTENT` can be unset or empty to write an empty file.


Usage
-----

```sh
# Write a single line without EOL
ENV2FILE_CONTENT=0.14.0-rc1 ENV2FILE_TO=.terraform-version ./env2file

# Write multiple lines
ENV2FILE_CONTENT=$'[rebase]\n\tautoStash = true\n' ENV2FILE_TO=~/.gitconfig ./env2file

# Create an empty file in a not yet created directory
ENV2FILE_TO=build/.gitkeep ./env2file

# Do nothing and be verbose.
./env2file -v

# Write file only if it's not existent
ENV2FILE_CONTENT=-L ENV2FILE_TO=~/.curlrc ./env2file --no-clobber
```
