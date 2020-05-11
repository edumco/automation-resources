# APT

## Freezing apt packages

- List all installed packages with version

```bash
dpkg-query --show | awk '{print $1 "=" $2}'
```

- Save list to a file

```bash
dpkg-query --show | awk '{print $1 "=" $2}' > packages.txt
```

- Install package list using xargs

```bash
xargs -a packages.txt sudo apt-get install -V
```
