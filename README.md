# .bashrc.d
My `~/.bashrc` hacks!  
Better organized in a dedicated directory :)

## How To

- clone this repo
- link/move this repo's root directory to `~/.bashrc.d`
- add a short script to `~/.bashrc` to source each file

## Script to add to .bashrc
A similar script might be already there (for example on Fedora).  
If this is the case, simply modify it to source only those files ending in `.sh`:

```bash
# User specific aliases and functions
if [ -d ~/.bashrc.d ]; then
  #for rc in ~/.bashrc.d/*; do
  for rc in ~/.bashrc.d/*.sh; do
    if [ -f "$rc" ]; then
      source "$rc"
    fi
  done
fi

unset rc
```

A simpler version:

```bash
for RC_FILE in ~/.bashrc.d/*.sh
do source "$RC_FILE"
done
```
