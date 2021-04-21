# Configurations

### What is an Electric Configuration?
_**❓ Tip: Use the [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=Electric.electric-language-support) Extension For Snippets And Syntax Highlighting For Electric Configurations**_

_**❗ Important: Each header must have spaces on both sides**_

_**[Info] is incorrect! [ Info ] is the correct notation.**_

_**❓ Tip: Use the `electric gen` command to automatically generate a configuration from your current environment.**_

An electric configuration is a `.electric` file which contains packages installed from different package providers (and package managers), all in one place.

## Language Guide

Electric configurations are quite similar to the `toml` format.

An electric configuration is nothing but a list of key value pairs, which is then parsed by electric.

`package-name => 1.0.0`

`=>` acts as the assigning operator.

`package-name` is the key and `1.0.0` is the value.

Comments are denoted with a `#` or a hashtag. Note that inline commands are **not** supported.

```toml
# this installs `somepackage` version 1
somepackage => 1.0.0 # inline comments not supported, don't use this!
```

## `[ Info ] (Required)`



Information about the `.electric` configuration.

### Options

------------------------


`Publisher`

The publisher of the configuration.

Example:

```toml
[ Info ] # Not [Info]
Publisher => "XtremeDevX"
```
------------------------

`Description`

A description of the configuration.

Example:

```toml
[ Info ] # Not [Info]
Publisher => "XtremeDevX"
Description => "My Python Development Environment!"
```

## `[ Packages ]`

Packages that electric will install.

Example:

```toml
[ Packages ]
# with version
7-Zip => 19.00
# without version
atom
```

## `[ Editor ]`

Information about a code editor that might be included in the electric configuration.

### Options
------------------------


`Editor`

Name of the code editor that is in the configuration. Here's a list of currently supported code editors.

```
Visual Studio Code
Visual Studio Code Insiders
Sublime Text 3*
Atom
```
*Currently Sublime Text 3 Support Limited to Plugin Installation

## `[ Editor-Extensions ]`
Extensions for the `Editor` specified under `[ Editor-Extensions ]`.

Example:
```toml
[ Editor ]
Editor => "Visual Studio Code"

[ Editor-Extensions ]
# with specific version
electric.electric-language-support => 0.0.7 
# without version
pkief.material-icon-theme
# installs latest version automatically
esbenp.prettier-vscode
```

## `[ Pip-Packages ]`

Electric will install all python (pip) packages specified in this header. Here's an example.

```toml
[ Pip-Packages ]
# with version
requests => 2.25.1
# without version
click
```

Electric will use `pip` to install all the packages specified under the `[ Pip-Packages ] section.

## `[ Node-Packages ]`

Electric will install all nodejs (npm) packages specified in this header. Here's an example.

```toml
[ Node-Packages ]
# with version
express => 4.17.1
# without version
rando.js
```

Electric will use `npm` to install all the packages specified under the `[ Node-Packages ] section.

## TurboIn Notation

Sharing large environments with hundreds (or even thousands) of packages can be time-taking and tedious.

Electric provides TurboIn notation (Short For Turbo Insert) which allows you to get a list of packages from all sorts of package managers.

Here's a list of supported TurboIn Operators.

```toml
# Electric (List Installed Package With Electric)
<electric>
<electric:name>
<electric:name,version> # include versions

# Python (List Package From pip)
<pip>
<pip:name>
<pip:name,version> # include versions
<python>
<python:name>
<python:name,version> # include versions

# NodeJS (List Package From npm)
<npm>
<npm:name>
<npm:name,version> # include versions
<node:name>
<node>
<node:name,version> # include versions

# Visual Studio Code (List Packages from vscode)
<vscode>
<vscode:name>
<vscode:name,version> # include versions

# Visual Studio Code Insiders (List Packages from vscode-insiders)
<vscode-insiders>
<vscode-insiders:name>
<vscode-insiders:name,version> # include versions

# Atom (List Packages from atom)
<atom>
<atom:name>
<atom:name,version> # include versions
<apm>
<apm:name>
<apm:name,version> # include versions

# Sublime Text 3 (List Packages from sublime text 3)
<sublime>
<sublime:name>
```

Usage

```toml
[ Packages ]
# insert all electric packages without version
<electric> 

[ Pip-Packages ]
# insert all python packages with version
<pip:name,version>
```

To insert the data into the turboins, simply run `electric sign myconfiguration.electric`.

## Managing Configurations

### Sign Your Configuration
Run `electric sign myconfig.electric` to sign your configuration so that you can share it. 

This verifies that all the packages specified in the configuration are valid and adds 2 checksums to the end of your configuration.


### Install A Signed Configuration

Then run `electric config myconfig.electric` to install the configuration.


#### Include Versions For Config Installation

Versions are ignored by default unless electric is explicitly told to install these specific versions.

If you want to include the versions specified for each package in the configuration use the `--include-versions` flag on the `electric config` command.`

### Uninstall A Signed Configuration

You can run `electric config --uninstall myconfig.electric` to uninstall or remove all contents of the configuration.
