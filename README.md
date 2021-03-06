# opal-autoloader
No need to write those
```ruby
require "this"
require "that"
```
in your opal code everywhere.

## install

add the following to Gemfile:
```ruby
gem 'opal-autoloader'
```
and `bundle install`

## usage

after loading opal
```ruby
require 'opal-autoloader'
```
Of course, it must be made sure, that used files are included during compilation, for example by using:
```ruby
require_tree 'components'
```

## configuration
The look up paths can be adjusted, here the default:
```ruby
Opal::Autoloader.load_paths = %w[components models operations stores]
```
These are the module path prefixes as used in the `Opal.modules` array.
Constants will be looked up there, if they cannot be found directly.
For example a constant `My::Component` will be looked up in Opal.modules directly, in the module 'my/component',
if it cannot be found there, it will be looked up as 'components/my/component', and so on.

## info
This has been extracted from the ruby-hyperloop project and is originally a port of the rails autoloader.

## community

Lets meet in the ruby-hyperloop gitter channel.
