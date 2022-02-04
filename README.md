# dev-public-utils
Random public utilities. Mainly public support files and explanatory code gists.

# Styleguides

## Rubocop
To use the rubocop suggested common rules, add a `.rubocop.yml` file at the root of your project with the following content
```
inherit_from:
  - https://raw.githubusercontent.com/qmee/dev-public-utils/main/styleguides/rubocop.yml

```

If you wish to override specific rules, just add them under this inherit block according to rubocop documentation.

To use the different set of rules for spec files, add an additional `.rubocop.yml` file to your `spec/` folder with the following content
```
inherit_from:
  - https://raw.githubusercontent.com/qmee/dev-public-utils/main/styleguides/rubocop-specs.yml
```
As with regular cops, any overrides can be added after this block.