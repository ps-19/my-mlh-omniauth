# MLH/my-mlh-omniauth

[![Build Status](https://travis-ci.org/MLH/my-mlh-omniauth.svg?branch=master)](https://travis-ci.org/MLH/my-mlh-omniauth)

This is the official [OmniAuth](https://github.com/omniauth/omniauth) strategy for
authenticating with [MyMLH](https://my.mlh.io). To use it, you'll need to
[register an application](https://my.mlh.io/oauth/applications) and obtain a OAuth Application ID and Secret from MyMLH.

It now supports MyMLH API V3. [Read the MyMLH V3 docs here](https://my.mlh.io/docs).

Once you have done so, you can follow the instructions given below:

## Requirements

You need to have at least Ruby 2.2.4 to use this gem.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'omniauth-mlh'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install omniauth-mlh

## Usage (Rack)

```ruby
use OmniAuth::Builder do
  provider :mlh, ENV['MY_MLH_KEY'], ENV['MY_MLH_SECRET'], scope: 'default email birthday'
end
```

## Usage (Rails with Devise)

```ruby
# config/devise.rb

Devise.setup do |config|
  config.provider :mlh, ENV['MY_MLH_KEY'], ENV['MY_MLH_SECRET'], scope: 'default email birthday'
end
```

## Contributing

1. Fork it ( https://github.com/mlh/my-mlh-omniauth/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Credit

We used part of [datariot/omniauth-paypal](http://github.com/datariot/omniauth-paypal)'s code to help us test this gem.

## Questions?

Have a question about the API or this library? Start by checking out the
[official MyMLH documentation](https://my.mlh.io/docs). If you still can't
find an answer, tweet at [@MLHacks](http://twitter.com/mlhacks) or drop an
email to [engineering@mlh.io](mailto:engineering@mlh.io).
