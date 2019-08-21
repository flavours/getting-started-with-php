# Flavour for PHP - Getting started

This is a minimal project to explain how to use flavour with PHP. It contains a `flavour.yml` file that is the basis for your project.
Flavour for PHP uses composer in the background, and will automatically manage addons which will be installed to your `flavour.yml` and `composer.json` file.

_You will need **flavour-cli** to be installed_

No files are needed to make flavour work in your PHP project. Just execute your flavour commands in your project root and it will automatically create or adjust all configuration files.

The `samples` folder contains some sample yaml files that show possible options if you intend to build your own packages or registry or install from a different source.


## Adding packages

To add a package to your project using `flavour-cli`

```
#  Add package from registry to your project
flavour add composer/package-namespace/package-name

# use a specific addon manager and a custom flavour.yml
flavour add  --addonmanager=flavour/fam-php-laravel --package=../test.php.yml
```

The namespace for php packages is `composer` which has to be the first part of the package identifier.

Flavour will try to automatically detect the ideal installation scenario. Dev packages should therefore be installed only to `require-dev` and custom install scripts will prepare your environment to customize package configurations.

If you need to install a specific version of a package you can do so by adding the version to the package name

```
flavour add composer/package-namespace/package-name:v1.2.3
```

This can also be used to change an already installed version.

## Remove packages

Removing packages works the same way adding does

```
#  Remove package from registry to your project
flavour remove composer/package-namespace/package-name
```

## References

* Flavour CLI: https://www.npmjs.com/package/@flavour/cli
* fam-php: https://gitlab.com/divio/flavour/addon-managers/fam-php
* fam-php-laravel: https://gitlab.com/divio/flavour/addon-managers/fam-php-laravel
