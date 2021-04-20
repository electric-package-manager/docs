# Uninstall Command

### Usage:


```
electric uninstall <packages> <flags>
```

### Help:

```
Usage: electric uninstall [OPTIONS] [PACKAGE_NAME]

  Uninstall a package or a list of packages.

Options:
  -m, --manifest TEXT          Read from a manifest file instead of querying
                               from the community repository

  -v, --verbose                Enable verbose mode for uninstallation
  -d, --debug                  Enable debug mode for uninstallation
  -nc, --no-color              Disable colored output for uninstallation
  -l, --log-output TEXT        Log output to the specified file
  -y, --yes                    Accept all prompts during uninstallation
  -s, --silent                 Completely silent uninstallation without any
                               output to console

  -py, --python                Specify a Python package to uninstall
  -ato, --atom                 Specify an Atom extension to uninstall
  -vs, --vscode                Specify a Visual Studio Code extension to
                               uninstall

  --nightly, --pre-release     Specify a Visual Studio Code extension to
                               uninstall

  -npm, --node                 Specify a Python package to uninstall
  -p, --portable, --non-admin  Uninstall a portable version of a package
  -pg, --plugin                Uninstall a plugin of a package
  -cf, --configuration         Specify a config file to uninstall
  -?, -h, --help               Show this message and exit.
```

### Flags:


`--manifest` | `-m`

Uninstall directly from a manifest | json file stored locally.

Example:

`electric uninstall --manifest docker-desktop.json`

------------------------------------

`--verbose` | `-vb`

Enable verbose mode for installation.

Example:

`electric uninstall sublime-text-3 --verbose`

------------------------------------

`--debug` | `-d`

Enable debug mode for installation.

Example:

`electric uninstall 7-Zip --debug`

------------------------------------

`--no-color` | `-nc`

Disable colored output for installation.

Example:

`electric uninstall --no-color visual-studio-code`

------------------------------------

`--log-output` | `-l`

Log output to the specified file.

Example:

`electric uninstall yarn --log-output C:\Users\bob\Desktop\uninstall.log`

------------------------------------

`--yes` | `-y`

Accept any prompts during installation.

Example:

`electric uninstall discord --yes`

------------------------------------

`--silent` | `-s`

Enable silent mode for installation.

Example:

`electric uninstall anydesk --silent`

------------------------------------

`--python` | `-py`

Uninstall a Python (pip) package.

Example:

`electric uninstall --python requests`

------------------------------------

`--atom` | `-ato`

Uninstall a Atom extension.

Example:

`electric uninstall --atom dracula-syntax`

------------------------------------

`--node` | `-npm`

Uninstall a node (npm) package.

Example:

`electric uninstall --node express`

------------------------------------

`--vscode` | `-vs`

Uninstall a Visual Studio Code extension.

Example:

`electric uninstall --vscode pkief.material-icon-theme`

------------------------------------

`--nightly` | `--pre-release`

Uninstall a nightly / pre-release build of a package.

Example:

`electric uninstall atom --nightly`

------------------------------------


`--portable` | `--non-admin` | `-p`

Install a portable or non-admin version of a package.

Example:

`electric install sublime-text-3 --portable`

------------------------------------

`--plugin` | `-pl`

Uninstall a plugin or extension for electric.

Example:

`electric uninstall --plugin auto-update`

------------------------------------

`--configuration` | `-cf`

Uninstall an electric configuration.

Example:

`electric uninstall --configuration C:\Users\bob\Desktop\electric-configuration.electric`

------------------------------------

## How It Works

Electric scans thousands of entries and keys in the Windows registry to find the software's `UninstallString`. It then runs the `UninstallString` with silent switches to uninstall the software silently, and without prompts.

