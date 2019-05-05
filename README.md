# Bash, the good path

Errors will not stop the execution unless `set -o errexit` is applied. 

Use `set -o nounset`, this will make any expansions of unset variables as error.

This will protect you against unset variables.

Using `?` expansion can protect you against unset or empty variables. This will output an error message if empty/unset and treat expansion as an error.

`rm -rf "${build:?Error, variable is empty or unset}``

`set -f`
Disable filename expansion (globbing) upon seeing *, ?, etc. Don't use this if you rely on globbing.




# Resources

- https://github.com/awesome-lists/awesome-bash
