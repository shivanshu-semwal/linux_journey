# Some Command line tricks

---

- `xargs -p [command]` prompts for the execution of the command

- `xargs -I % [command %]` replaces the % with the arguments passed

---

- `ls -1` print file names in one column

---

- `ls -1 | sed -e 's/\.svg$//'` printing only filenames not the extensions of .svg files

---