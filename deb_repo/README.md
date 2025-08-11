# deb builder

Updated regularly

Main workflow:

1. Create the actual working directories and files
2. Copy files
3. Build the .deb package

The working directories allow user customization or a full rebuild, e.g., `/lib/systemd/system/hubv3.service`.

## Clean all working artifacts
```bash
./build.sh --clean
```

Different .deb builds created by users do not interfere with each other.

## Rebuild
```bash
./build.sh --rebuild
```

Deletes data under the working directories and recreates them; user data is typically reset.

During rebuild, some files in this directory are copied into the working directories.

## Build
```bash
./build.sh
```

Builds the .deb package.

In general, if a file already exists in the working directory, it will not be overwritten by the file from this directory. This facilitates manual editing until the `--rebuild` command is used.

