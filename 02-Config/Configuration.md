# Configurations

### What is an Electric Configuration?

An electric configuration is a `.electric` file which contains packages installed from different package providers (and package managers), all in one place.

## Language Guide

Electric configurations are quite similar to the `toml` format.

An electric configuration is nothing but a list of key value pairs, which is then parsed by electric.

`package-name => v1.0.0`

`=>` acts as the assigning operator.

## Headers

`[ Info ]`

Information about the `.electric` configuration.

### Options

Publisher

The publisher of the configuration.

Example:

```toml
Publisher => "XtremeDevX"
```
------------------------

Description

A description of the configuration.

Example:

```toml
Description => "This is a description of the configuration!"

```