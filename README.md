# dev-public-utils

Random public utilities. Mainly public support files and explanatory code gists.

## Styleguides

### Rubocop

#### **Rubocop installation and setup**

Install Rubocop globally to your machine:

```console
gem install rubocop
```

To use the rubocop suggested common rules, add a `.rubocop.yml` file at the root of your project with the following content

```yaml
inherit_from:
  - https://raw.githubusercontent.com/qmee/dev-public-utils/main/styleguides/rubocop.yml
```

If you wish to override specific rules, just add them under this inherit block according to rubocop documentation.

To use the different set of rules for spec files, add an additional `.rubocop.yml` file to your `spec/` folder with the following content

```yaml
inherit_from:
  - ../.rubocop.yml
  - https://raw.githubusercontent.com/qmee/dev-public-utils/main/styleguides/rubocop-specs.yml
```

As with regular cops, any overrides can be added after this block.

**IMPORTANT!** You are heavily encouraged to add the following to your `.gitignore` file to avoid committing noisy rubocop cached files

#### **`.gitignore`**

```console
.rubocop-https*
```

#### **VSCode integration**

1. Install the [ruby-rubocop VSCode extension](https://marketplace.visualstudio.com/items?itemName=misogi.ruby-rubocop)
2. Go to File -> Preferences -> Settings
3. Search for `Rubocop`. You should see the `Rubocop: Execute Path` setting
4. Find your gem installation folder by running `gem environment gemdir` in your terminal
5. Navigate to this path and find the `/exe` folder for the rubocop gem (e.g. from the installation folder I navigated to `/gems/rubocop-1.29.1/exe`)
6. Paste the full path to the `/exe` folder into the `Rubocop: Execute Path` setting
7. If your `Rubocop: On Save` setting is enabled, the Rubocop linter will run on save. Alternatively run `rubocop` in your terminal to lint all files in the repository.
