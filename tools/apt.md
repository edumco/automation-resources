# APT

## Freezing apt packages

- List all installed packages with version

```bash
dpkg -l | grep '^ii' | awk '{print $2 "=" $3}'
```

- Save list to a file

```bash
dpkg -l | grep '^ii' | awk '{print $2 "=" $3}' > packages.txt
```

- Install package list using xargs

```bash
xargs -a packages.txt sudo apt-get install -V
```
