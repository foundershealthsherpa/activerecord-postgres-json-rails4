# activerecord-postgres-json-rails4

Based off https://github.com/romanbsd/activerecord-postgres-json, including
changes from rails-4-support branch
https://github.com/nzifnab/activerecord-postgres-json/tree/rails-4-support

Gem name changed from the original to allow it to be included in gemspec
file of other gems, which doesn't allow specifying github sources with
specific branches.

A minimal JSON/JSONB column type support for ActiveRecord 3.2.x through 4.1.x
This gem adds the following support:

1. Using json/jsonb column type in migrations, e.g. `add_column :foo, :bar, :json` or `add_column :foo, :bar, :jsonb`
2. json field support in the schema definitions
3. JSON coder for using with the `serialize` class method:

```ruby
class User < ActiveRecord::Base
  serialize :settings, ActiveRecord::Coders::JSON
  serialize :settings, ActiveRecord::Coders::JSON.new(symbolize_keys: true) # for symbolize keys
end

User.first.settings.class # => Hash
User.first.settings[:show_popups] # => true
...
```

## Contributing to activerecord-postgres-json

See https://github.com/romanbsd/activerecord-postgres-json#contributing-to-activerecord-postgres-json

## Copyright

Copyright (c) 2014 Roman Shterenzon. See LICENSE.txt for
further details.

