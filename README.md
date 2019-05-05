# Bash, the good path

Errors will not stop the execution unless `set -o errexit` is applied. 

Use `set -o nounset`, this will make any expansions of unset variables as error.

This will protect you against unset variables.

Using `?` expansion can protect you against unset or empty variables. This will output an error message if empty/unset and treat expansion as an error.

`rm -rf "${build:?Error, variable is empty or unset}`

`set -f`
Disable filename expansion (globbing) upon seeing *, ?, etc. Don't use this if you rely on globbing.

`set -o pipefail` causes a pipeline (for example, curl -s https://yahoo.fr/ | grep yahoo) to produce a failure return code if any command returns an error. Normally, pipelines only return a failure if the last command returns an error. 

Whenever you pass a variable to a command, you should probably quote it. Otherwise, the shell will perform word-splitting and globbing, which is likely not what you want.


## Testing

- https://github.com/sstephenson/bats

## Linting

- https://github.com/koalaman/shellcheck

# Resources

- https://google.github.io/styleguide/shell.xml

- https://github.com/awesome-lists/awesome-bash

- https://mywiki.wooledge.org/BashPitfalls

- About using TCL instead of bash https://news.ycombinator.com/item?id=14325048

- The POSIX Shell And Utilities http://shellhaters.org/
