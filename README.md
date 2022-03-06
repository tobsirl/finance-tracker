# README

"This is the finance tracker app from the Complete Ruby on Rails Developer course"

## Basic setup

1. Setup route `root 'welcome#index'`
2. Setup up welcome controller with method index
3. Setup a view `index.html.erb`

## Installing devise

1. Install the gem

```ruby
  gem 'devise'
```

2. Run the install command

```bash
  rails generate devise:install
```

3. Run the following to create routes for User

```bash
  rails generate devise User
```

This will generate

```bash
  rails routes | grep users
                        new_user_session GET    /users/sign_in(.:format)                                                                          devise/sessions#new
                            user_session POST   /users/sign_in(.:format)                                                                          devise/sessions#create
                    destroy_user_session DELETE /users/sign_out(.:format)                                                                         devise/sessions#destroy
                       new_user_password GET    /users/password/new(.:format)                                                                     devise/passwords#new
                      edit_user_password GET    /users/password/edit(.:format)                                                                    devise/passwords#edit
                           user_password PATCH  /users/password(.:format)                                                                         devise/passwords#update
                                         PUT    /users/password(.:format)                                                                         devise/passwords#update
                                         POST   /users/password(.:format)                                                                         devise/passwords#create
                cancel_user_registration GET    /users/cancel(.:format)                                                                           devise/registrations#cancel
                   new_user_registration GET    /users/sign_up(.:format)                                                                          devise/registrations#new
                  edit_user_registration GET    /users/edit(.:format)                                                                             devise/registrations#edit
                       user_registration PATCH  /users(.:format)                                                                                  devise/registrations#update
                                         PUT    /users(.:format)                                                                                  devise/registrations#update
                                         DELETE /users(.:format)                                                                                  devise/registrations#destroy
                                         POST   /users(.:format)                                                                                  devise/registrations#create

```

### Generate the UserStock association with this command

```
rails g resource UserStock user:references stock:references
```

#### Endpoints
```
/user -> user_path(user: user)
/user/:id => user_path(user)
```