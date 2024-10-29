### copy this code into your .bashrc or .zshrc file
```bash
mcd() { mkdir "$@" 2> >(sed s/mkdir/mcd/ 1>&2) && cd "$_"; }
```
