# Puppet::ResourceApi [![TravisCI Build Status](https://travis-ci.org/puppetlabs/puppet-resource_api.svg?branch=master)](https://travis-ci.org/puppetlabs/puppet-resource_api) [![Appveyor Build status](https://ci.appveyor.com/api/projects/status/8o9s1ax0hs8lm5fd/branch/master?svg=true)](https://ci.appveyor.com/project/puppetlabs/puppet-resource-api/branch/master)
 [![codecov](https://codecov.io/gh/puppetlabs/puppet-resource_api/branch/master/graph/badge.svg)](https://codecov.io/gh/puppetlabs/puppet-resource_api)


This is an implementation of the [Resource API](https://github.com/DavidS/puppet-specifications/blob/resourceapi/language/resource-api/README.md) proposal. Find a working example of a new-style provider in the [experimental puppetlabs-apt branch](https://github.com/DavidS/puppetlabs-apt/blob/resource-api-experiments/lib/puppet/provider/apt_key2/apt_key2.rb). There is also the corresponding [type](https://github.com/DavidS/puppetlabs-apt/blob/resource-api-experiments/lib/puppet/type/apt_key2.rb), [provider](https://github.com/DavidS/puppetlabs-apt/blob/resource-api-experiments/lib/puppet/provider/apt_key2/apt_key2.rb), and [new unit tests](https://github.com/DavidS/puppetlabs-apt/blob/resource-api-experiments/spec/unit/puppet/provider/apt_key2/apt_key2_spec.rb) for 100% coverage.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'puppet-resource_api'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install puppet-resource_api

## Usage

The [Resource API](https://github.com/DavidS/puppet-specifications/blob/resourceapi/language/resource-api/README.md) explains the usage and capabilities of this gem.

Already working:
* basic type and provider definition, using `name`, `desc`, and `attributes`
* the `canonicalize` and `remote_resource` features
* all the logging facilities
* executing the new provider under any of the following commands:
  * `puppet apply`
  * `puppet resource`
  * `puppet agent`
  * `puppet device` (if applicable)


There are still a few notable gaps between the implementation, and the specification:
* Only a single runtime environment (the puppet commands) is currently implemented.
* `auto*` definitions
* the Commands API is mostly implemented, but deployment is blocked on upstream work (PDK-580). You can use regular Ruby `system()` calls as a workaround, with all their attendant encoding, and safety issues.

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/puppet-resource_api.
