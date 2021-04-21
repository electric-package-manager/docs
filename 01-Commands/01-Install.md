# Install Command

### Usage:

```
electric install <packages> <flags>
```

### Help:

```
> electric install --help
Usage: electric install [OPTIONS] [PACKAGE_NAME]

  Install a package or a list of packages.

Options:
  -v, --version TEXT           Install a certain version of a package
  --nightly, --pre-release     Install a nightly or pre-release build of a
                               package

  -p, --portable, --non-admin  Install a portable version of a package
  -vb, --verbose               Enable verbose mode for installation
  -d, --debug                  Enable debug mode for installation
  -np, --no-progress           Disable progress bar for installation
  -up, --update                Update electric before installation
  -nc, --no-color              Disable colored output for installation
  -l, --log-output TEXT        Log output to the specified file
  -dir, --install-dir TEXT     Specify an installation directory for a package
  -vc, --virus-check           Check for virus before installation
  -y, --yes                    Accept all prompts during installation
  -s, --silent                 Completely silent installation without any
                               output to console

  -vs, --vscode                Specify a Visual Studio Code extension to
                               install

  -sb, --sublime               Specify a Sublime Text 3 extension to install
  -ato, --atom                 Specify an Atom extension to install
  -py, --python                Specify a Python package to install
  -npm, --node                 Specify a Npm package to install
  -sc, --sync                  Force downloads and installations one after
                               another

  -rd, --reduce                Cleanup all traces of package after
                               installation

  -rl, --rate-limit INTEGER
  -f, --force                  Force install a package, ignoring any existing
                               installations of a package.

  -cf, --configuration         Specify a config file to install
  -pl, --plugin                Specify a plugin to install
  -m, --manifest TEXT          Read from a manifest file instead of querying
                               from the community repository

  -?, -h, --help               Show this message and exit.
```

### Flags:

`--version` | `-v`

Install a specific version of a package.

Example:

`electric install atom --version 1.53.0`

------------------------------------

`--nightly` | `--pre-release`

Install a nightly / pre-release build of a package.

Example:

`electric install atom --nightly`

------------------------------------

`--portable` | `--non-admin` | `-p`

Install a portable or non-admin version of a package.

Example:

`electric install sublime-text-3 --portable`

------------------------------------

`--verbose` | `-vb`

Enable verbose mode for installation.

Example:

`electric install sublime-text-3 --verbose`

------------------------------------

`--debug` | `-d`

Enable debug mode for installation.

Example:

`electric install 7-Zip --debug`

------------------------------------

`--no-progress` | `-np`

Disable progress bar for installation.

Example:

`electric install 7-Zip --no-progress`

------------------------------------

`--update` | `-up`

Update electric package list before installation.

Example:

`electric install --update visual-studio-code`

------------------------------------

`--no-color` | `-nc`

Disable colored output for installation.

Example:

`electric install --no-color visual-studio-code`

------------------------------------

`--log-output` | `-l`

Log output to the specified file.

Example:

`electric install yarn --log-output C:\Users\bob\Desktop\install.log`

------------------------------------

`--install-dir` | `-dir`

Specify a directory to install a package to.

Example:

`electric install yarn --install-dir C:\Users\bob\Desktop\NewApps`

------------------------------------

`--virus-check` | `-vc`

Check the downloaded installer for viruses using the virustotal api.

Example:

`electric install anydesk --virus-check`

------------------------------------

`--yes` | `-y`

Accept any prompts during installation.

Example:

`electric install discord --yes`

------------------------------------

`--silent` | `-s`

Enable silent mode for installation.

Example:

`electric install anydesk --silent`

------------------------------------

`--vscode` | `-vs`

Install a Visual Studio Code extension.

Example:

`electric install pkief.material-icon-theme --vscode`

------------------------------------

`--sublime` | `-sb`

Install a Sublime Text 3 plugin.

Example:

`electric install --sublime "Dracula Color Theme"`

------------------------------------


`--atom` | `-ato`

Install a Atom extension.

Example:

`electric ininstall --atom dracula-syntax`

------------------------------------


`--python` | `-py`

Install a Python (pip) package.

Example:

`electric install --python requests`

------------------------------------

`--node` | `-npm`

Install a node (npm) package.

Example:

`electric install --node express`

------------------------------------

`--sync` | `-sc`

Install multiple packages synchronously instead of concurrently (at the same time).

Example:

`electric install firefox,go --sync`

------------------------------------

`--reduce` | `-rd`

Cleanup all downloaded files and installers after installation.

Example:

`electric install heroku --reduce`

------------------------------------

`--rate-limit` | `-rl`

Limit the rate at which files are downloaded for installation.

Example:

`electric install pycharm --rate-limit 500`

------------------------------------

`--force` | `-f`

Override checksum verification and ignore any existing installations of the package.

Example:

`electric install pycharm --force`

------------------------------------

`--configuration` | `-cf`

Install an electric configuration.

Example:

`electric install --configuration C:\Users\bob\Desktop\electric-configuration.electric`

------------------------------------

`--plugin` | `-pl`

Install a plugin or extension for electric.

Example:

`electric install --plugin auto-update`

------------------------------------

`--manifest` | `-m`

Install directly from a manifest | json file stored locally.

Example:

`electric install --manifest docker-desktop.json`

------------------------------------

## How It Works

In simple terms, electric downloads the installer from the `url` , verifies its `checksum` and invokes the downloaded installer with the `install-switches`, allowing for silent, no-prompt installation.


