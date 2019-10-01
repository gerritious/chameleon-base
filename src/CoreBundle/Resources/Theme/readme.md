# Building the CoreUI Theme for Chameleon

## CoreUI as Requirement in `composer.json`

Please require CoreUI in your `composer.json`:

`composer require coreui/coreui`


## Scripts

You will find scripts to build all CoreUI assets including overrides for Chameleon in:
`vendor/chameleon-system/chameleon-base/src/CoreBundle/Resources/Theme/package.json`.

Call these scripts from within the project's root directory (usually `customer`) by typing:

`npm --prefix vendor/chameleon-system/chameleon-base/src/CoreBundle/Resources/Theme/ run <script-name>`

Example: `npm --prefix vendor/chameleon-system/chameleon-base/src/CoreBundle/Resources/Theme/ run css`

**Please make sure** to always call these scripts from within your project's root directory and provide the path to the theme's `package.json` file as a value to the `prefix` option as shown above. This ensures that scripts run properly in docker environments.

The following scripts will be usefull during develoment:

1. `build` Please call this script to re-install CoreUI. It will execute the following steps:
  * Install all requirements for the build process of CoreUI
  * Install all CoreUI requirements and assets
  * Install 'Perfect Scrollbar'
  * Copy all necessary files for 'Perfect Scrollbar' to the theme directory
  * Copy CoreUI's JavaScript files to chameleon's theme directory
  * Run the `css` command (see below)

2. `css` Please call this script whenever you make changes to your custom scss sources. It will perform the following steps:
  * Lint scss sources to enforce conventions and avoid frequent errors
  * Compile scss sources to css
  * Minify the resulting css

The `package.json` file contains some other scripts that are not intended to be called separately.

## Target Directory
All resulting files can be found in the target directory:
`/vendor/chameleon-system/chameleon-base/src/CoreBundle/Resources/public/themes/coreui`

## Customization for Chameleon

Please add your styles and imports to `vendor/chameleon-system/chameleon-base/src/CoreBundle/Resources/public/themes/standard/src/scss/styles.scss` to customize the CoreUI theme.