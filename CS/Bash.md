# The Set Builtin
https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html

```shell
# set -_ enable command
# set +_ disable command

set -x # print executed command
set -e # immediately exit if any command has a non-zero exit status
set -u # immediately exit if use udefind variable
set -o pipefail # immediately exit if masked pipline error
```