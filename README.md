# Local Packages Manager (localpac)

`localpac` is a command-line tool for managing local packages across multiple programming languages, including Python, Ruby, and Go. It allows users to install, uninstall, list, and manage packages in their virtual enviroments.

## Table of Contents
- [Usage](#usage)
- [Options](#options)
- [Examples](#examples)
- [Notes](#notes)
- [Installation](#installation)
- [Functions](#functions)

## Usage
```bash
localpac [options] [package_names]
```
Use `localpac -h` for help.

## Options
- `-S`                Install the specified packages.
- `-R`                Remove the specified packages.
- `-P <prefix>`       Add a prefix to the installed package's executables.
- `-L <link_to>`      Create a symbolic link from the package's virtual environment.
- `-l`                List installed packages.
- `-p`                Specify Python as the package's language (optional).
- `-r`                Specify Ruby as the package's language (optional).
- `-g`                Specify Go as the package's language (optional).
- `-h`                Display this help menu.

## Examples
```bash
localpac -l                                 # List all installed packages.
localpac -l -p                              # List all installed Python packages.
localpac -S package_names                   # Install a package.
localpac -S https://github.com/user/project # Install a package from GitHub by link.
localpac -S user/project                    # Install a package from GitHub by user/project.
localpac -S -r package_names                # Install a Ruby package.
localpac -R package_names                   # Remove a package.
localpac -R -p package_names                # Remove a Python package.
localpac -P myprefix- package_names         # Add a prefix to package commands.
localpac -S -P myprefix- package_names      # Install a package and prefix its commands.
localpac -L /link/to/dir package_names      # Link package's directory to link/to/dir.
localpac -S -g -L ~/tools package_repos     # Install Go packages, and link to ~/tools/package_names.
localpac -R -r -L ~/tools package_names     # Uninstall Ruby packages, unlink link at ~/tools/package_names.
localpac -S -r -L ~/ -P cmd- package_names  # Install Ruby packages, link to ~/ and prefix exec files with cmd-.
```

## Notes
- You can install packages directly from a Git repository by using its GitHub URL as the package name.
- If no language is specified, the script will automatically search for the package's language (this may be slower).
- If multiple languages are found for a package, you will be prompted to choose one.
- If using the `-L` flag with the `-R` flag, the specified packages will be unlinked from the selected directory.

## Installation
To install **localpac** run the command below and reload your terminal

`curl -L https://raw.githubusercontent.com/ThomasMTT/localpac/refs/heads/main/localpac --output localpac && chmod +x localpac && ./localpac - && mv localpac ~/.local/bin`

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.