### Friendly_Id
---
https://github.com/norman/friendly_id

```
http://example.com/states/washington
http://example.com/states/4323454

gem 'frindly_id', '~> 5.2.0'
bundle install
rails g friendly_id
rails db:migrate

```

```ruby
# app/models/user.rb
class User < ApplicationRecord
  extend FriendlyId
  friendly_id :name, use: :slugged
end

# app/controllers/users_controller.rb
class UserController < ApplicationController
  def show
    @user = User.friendly.find(params[:id])
  end
end

User.create! name: "Joe Schmoe"

User.find_each(&:save)
```

```
```


