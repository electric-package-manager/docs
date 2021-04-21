# Search Command

### Usage

```
electric search <package> <flags>
```

### Help:

```
> electric search --help
Usage: electric search [OPTIONS] APPROX_NAME

  Searches for a package in the official electric package repository.        

Options:
  -sw, --starts-with  Find packages which start with the specified literal   
  -e, --exact         Find packages which exactly match the specified literal
  -h, -?, --help      Show this message and exit.
```

### Flags:

`--starts-with` | `-sw`

Find a package that starts with the specified literal.

`electric search --starts-with ato` # Find `atom`

------------------------------------

`--exact` | `-e`

Find a package that exactly matches the specified literal word to word.

`electric search --exact atom` # Confirm that atom is the exact name of the package

------------------------------------
