# PDK RuboCop

[![Code Owners](https://img.shields.io/badge/owners-DevX--team-blue)](https://github.com/puppetlabs/pdk/blob/main/CODEOWNERS)
![ci](https://github.com/puppetlabs/pdk-rubocop/actions/workflows/ci.yml/badge.svg)

PDK RuboCop is a Gem that provides sane defaults to use when developing Puppet Content.

This gem was inspired by [voxpupuli-rubocop](https://github.com/voxpupuli/voxpupuli-rubocop)

## Usage

In your Gemfile, add the following:

```ruby
gem 'pdk-rubocop', '~> 0.1'
```

In your Rakefile, you can include the default Rake task:

```ruby
require 'pdk/rubocop/rake'
```

List your rake tasks with `bundle exec rake -T` 

```bash
rake rubocop                  # Run RuboCop
rake rubocop:autocorrect      # Autocorrect RuboCop offenses (only when it's safe)
rake rubocop:autocorrect_all  # Autocorrect RuboCop offenses (safe and unsafe)
```

To use the default config, create a `.rubocop.yml` and add the following:

```
---
inherit_gem:
  pdk-rubocop: module_rubocop.yml
```

After adding the inherited config, you may want to regenerate your todo file:

```
bundle exec rubocop --regenerate-todo
```
