# Update Command

### Usage:

```
electric update <packages> <flags>
```

### Help:

```
> electric update --help
Usage: electric.exe update [OPTIONS] PACKAGE_NAME

  Updates an existing package

Options:
  -np, --no-progress         Disable progress bar for bundle update
  -nc, --no-color            Disable colored output for bundle update
  -vb, --verbose             Enable verbose mode for update
  -l, --log-output TEXT      Log output to the specified file
  -d, --debug                Enable debug mode for updater
  -s, --silent               Completely silent update without any
                             output to console

  -vc, --virus-check         Check for virus before bundle update
  -rl, --rate-limit INTEGER
  -y, --yes                  Accept all prompts during update
  -rd, --reduce              Cleanup all traces of package after update

  -p, --portable             Update a portable version of a package
  -?, -h, --help             Show this message and exit.
```

------------------------------------

`--no-progress` | `-np`

Disable progress bar for update.

Example:

`electric update 7-Zip --no-progress`

------------------------------------


`--no-color` | `-nc`

Disable colored output for update.

Example:

`electric update --no-color visual-studio-code`

------------------------------------

`--verbose` | `-vb`

Enable verbose mode for update.

Example:

`electric update sublime-text-3 --verbose`

------------------------------------

`--log-output` | `-l`

Log output to the specified file.

Example:

`electric update yarn --log-output C:\Users\bob\Desktop\update.log`

------------------------------------

`--debug` | `-d`

Enable debug mode for update.

Example:

`electric update 7-Zip --debug`

------------------------------------

`--silent` | `-s`

Enable silent mode for update.

Example:

`electric update anydesk --silent`

------------------------------------

`--virus-check` | `-vc`

Check the downloaded installer for viruses using the virustotal api.

Example:

`electric update anydesk --virus-check`

------------------------------------

`--rate-limit` | `-rl`

Limit the rate at which files are downloaded for update.

Example:

`electric update pycharm --rate-limit 500`

------------------------------------

`--yes` | `-y`

Accept any prompts during update.

Example:

`electric update discord --yes`

------------------------------------

`--reduce` | `-rd`

Cleanup all downloaded files and installers after update.

Example:

`electric update heroku --reduce`

------------------------------------

`--portable` | `--non-admin` | `-p`

Update a portable or non-admin version of a package.

Example:

`electric update sublime-text-3 --portable`

------------------------------------
