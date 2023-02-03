# Installing Zig straight-forward way

## Your journey starts here

This is the first of the *letters for those just starting their zig dive, this is yet another tutorial on how to set up environments for zig using the tools you need to compose and execute your zig recipes.

---

## Linux :- Ubuntu

- Creating folder structure, these are mere examples of names and you are free to follow

```bash
mkdir 0.11.0-dev && cd 0.11.0-dev
```

- Downloading tar.xz

```bash
wget -c https://ziglang.org/builds/zig-linux-x86_64-0.11.0-dev.1507+6f13a725a.tar.xz
```

- Extracting and accessing content

```bash
tar -xJf zig-linux-x86_64-0.11.0-dev.1507+6f13a725a.tar.xz
cd zig-linux-x86_64-0.11.0-dev.1507+6f13a725a
```

- Adding new entry to PATH variable in **ZSH**

```bash
code ~/.zshrc
```

- Insert zig path as below in .zshrc

```text
export PATH=$HOME/zig_projects/0.11.0-dev/zig-linux-x86_64-0.11.0-dev.1507+6f13a725a:$PATH
```

```bash
source ~/.zshrc
```

## Ritual for Zig Language Server (zls)

### build + environment setting

To compose the the zls build, clone the master repository

```bash
git clone --recurse-submodules https://github.com/zigtools/zls
cd zls
zig build -Drelease-safe
```

- ZLS build generated for path:
/home/rodrigo/zig_projects/0.11.0-dev/zls/zig-out/bin

- Setting path for system recognize zls command.

```bash
code ~/.zshrc
```

Obs.: Insert zls path as below in .zshrc

```text
export PATH=$HOME/zig_projects/0.11.0-dev/zls/zig-out/bin:$PATH
```

```bash
source ~/.zshrc
```

- After configuring the path, just run the magic to enshrine the build version for zls:

```bash
zls --version
```

## Configure VSCode for ZIG and ZLS

- Open settings.json for your workspace/directory

    Open command pallete `Ctrl+Shit+P` search for Preferences:Open Workspace Settings(JSON)

    The following structure will be created:

    ```bash
    .vscode
    └── settings.json
    ```

- Insert the configuration below in **settings.json** and save

```json
{
    "zig.zigPath": "/home/user/zig_projects/0.11.0-dev/zig-linux-x86_64-0.11.0-dev.1507+6f13a725a/zig",
    "zls.path": "/home/user/zig_projects/0.11.0-dev/zls/zig-out/bin/zls",
    "[zig]": {
        "editor.defaultFormatter": "tiehuis.zig"
    }
}
```

- Reload VSCode `Ctrl+Shit+P`, search for Developer:Reload Window
