---
layout: post
title: "Creating a basic Rails application"
date: 2014-04-16 14:27:08 -0400
comments: true
categories: Rails, Ruby on Rails, Programming
---

I'm going to teach you how to create a basic rails application STEP BY STEP. There will be images and code for each step as well. I hope this works for you guys.

I know there are no tests written, but this is just for my students to create a 'scaffold' of controller/models.

There are a few dependencies as well:

- rvm
- Sublime text
- Sublime text alias (sub) that will open your project folder

In this first step, I want to create myself a new project folder. I am going to call this project "contact_list" as that is what we will be creating together, a 21st century Rolodex!

``` console
% cd ~/projects/
% mkdir contact_list
% cd contact_list
```

This next will will set up dependencies. Anyone who has been in a ruby project for long enough will know that RVM is huge. We will be using that in this project. To make gemset management easier, we will be creating a ".rvmrc" file.
``` console
% touch .rvmrc
% sub .
```

Inside of that ".rvmrc" file, we need to create our specific gemset. This command will force your computer to create the gemset if you haven't yet.

``` ruby    
rvm 2.1@contact_list --create
```

This command should reload your current directory. The following screenshot will display what output you SHOULD get. If you do not get it, you need to cd out of your directory, then CD back in.
``` console
    % cd .
```

{% img /images/2014-04-16/1_rvm_output.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Now, we are going to create our Rails project. To start, we need to install our Rails gem. After our gem is installed, we create a new project inside of our current directory with 'rails new .'.
``` console
    % gem install rails
    % rails new .

           exist
          create  README.rdoc
          create  Rakefile
          create  config.ru
          create  .gitignore
          create  Gemfile
          create  app
          create  app/assets/javascripts/application.js
          create  app/assets/stylesheets/application.css
          create  app/controllers/application_controller.rb
          create  app/helpers/application_helper.rb
          create  app/views/layouts/application.html.erb
          create  app/assets/images/.keep
          create  app/mailers/.keep
          create  app/models/.keep
          create  app/controllers/concerns/.keep
          create  app/models/concerns/.keep
          create  bin
          create  bin/bundle
          create  bin/rails
          create  bin/rake
          create  config
          create  config/routes.rb
          create  config/application.rb
          create  config/environment.rb
          create  config/secrets.yml
          create  config/environments
          create  config/environments/development.rb
          create  config/environments/production.rb
          create  config/environments/test.rb
          create  config/initializers
          create  config/initializers/backtrace_silencers.rb
          create  config/initializers/cookies_serializer.rb
          create  config/initializers/filter_parameter_logging.rb
          create  config/initializers/inflections.rb
          create  config/initializers/mime_types.rb
          create  config/initializers/session_store.rb
          create  config/initializers/wrap_parameters.rb
          create  config/locales
          create  config/locales/en.yml
          create  config/boot.rb
          create  config/database.yml
          create  db
          create  db/seeds.rb
          create  lib
          create  lib/tasks
          create  lib/tasks/.keep
          create  lib/assets
          create  lib/assets/.keep
          create  log
          create  log/.keep
          create  public
          create  public/404.html
          create  public/422.html
          create  public/500.html
          create  public/favicon.ico
          create  public/robots.txt
          create  test/fixtures
          create  test/fixtures/.keep
          create  test/controllers
          create  test/controllers/.keep
          create  test/mailers
          create  test/mailers/.keep
          create  test/models
          create  test/models/.keep
          create  test/helpers
          create  test/helpers/.keep
          create  test/integration
          create  test/integration/.keep
          create  test/test_helper.rb
          create  tmp/cache
          create  tmp/cache/assets
          create  vendor/assets/javascripts
          create  vendor/assets/javascripts/.keep
          create  vendor/assets/stylesheets
          create  vendor/assets/stylesheets/.keep
             run  bundle install
    Fetching gem metadata from https://rubygems.org/..........
    Fetching additional metadata from https://rubygems.org/..
    Resolving dependencies...
    Installing rake 10.3.0
    Using i18n 0.6.9
    Using json 1.8.1
    Using minitest 5.3.3
    Using thread_safe 0.3.3
    Using tzinfo 1.1.0
    Using activesupport 4.1.0
    Using builder 3.2.2
    Using erubis 2.7.0
    Using actionview 4.1.0
    Using rack 1.5.2
    Using rack-test 0.6.2
    Using actionpack 4.1.0
    Using mime-types 1.25.1
    Using polyglot 0.3.4
    Using treetop 1.4.15
    Using mail 2.5.4
    Using actionmailer 4.1.0
    Using activemodel 4.1.0
    Using arel 5.0.1.20140414130214
    Using activerecord 4.1.0
    Using bundler 1.6.1
    Installing coffee-script-source 1.7.0
    Installing execjs 2.0.2
    Installing coffee-script 2.2.0
    Using thor 0.19.1
    Using railties 4.1.0
    Installing coffee-rails 4.0.1
    Using hike 1.2.3
    Using multi_json 1.9.2
    Installing jbuilder 2.0.6
    Installing jquery-rails 3.1.0
    Using tilt 1.4.1
    Installing sprockets 2.11.0
    Using sprockets-rails 2.1.3
    Using rails 4.1.0
    Installing rdoc 4.1.1
    Installing sass 3.2.19
    Installing sass-rails 4.0.3
    Installing sdoc 0.4.0
    Installing spring 1.1.2
    Installing sqlite3 1.3.9
    Installing turbolinks 2.2.2
    Installing uglifier 2.5.0
    Your bundle is complete!
    Use `bundle show [gemname]` to see where a bundled gem is installed.
    Post-install message from rdoc:
    Depending on your version of ruby, you may need to install ruby rdoc/ri data:

    <= 1.8.6 : unsupported
     = 1.8.7 : gem install rdoc-data; rdoc-data --install
     = 1.9.1 : gem install rdoc-data; rdoc-data --install
    >= 1.9.2 : nothing to do! Yay!
             run  bundle exec spring binstub --all
    * bin/rake: spring inserted
    * bin/rails: spring inserted
```

Now, we're going to start our server to make sure everything is kosher. Let's start it and check it out!
``` console
% rails server
``` 

We have a rails project. This is the screen you guys should be getting. This is the "Welcome Aboard" message you get when you start every project.

{% img /images/2014-04-16/2_welcome_aboard.png 'Screenshot of stuff' 'Screenshot of stuff' %}

I want to get rid of the "Welcome Aboard" screen and start developing my own application, so I need to go into "config/routes.rb" and set up a root route. This will be where my application starts. For instance, if someone comes to my application at "www.nickscontactlist.com", this root route will be how it starts. The following code is telling it to go to a "Home" Controller's "Index" action.

``` ruby
Rails.application.routes.draw do
  root 'home#index'
end
```

After this, I refresh my page to see what it tells me. Remember, you need to code a little then test the output. 

{% img /images/2014-04-16/3_no_home_controller.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Awesome! This is the error I wanted. I need to initialize a Home Controller now! Remember, Controller's are generally pluralized! This one will be different. This is my landing page, hence "Home"

``` console
rails generate controller home

      create  app/controllers/home_controller.rb
      invoke  erb
      create    app/views/home
      invoke  test_unit
      create    test/controllers/home_controller_test.rb
      invoke  helper
      create    app/helpers/home_helper.rb
      invoke    test_unit
      create      test/helpers/home_helper_test.rb
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/home.js.coffee
      invoke    scss
      create      app/assets/stylesheets/home.css.scss
```

Awesome. I have my Home controller created. Let's refresh the page and see what happens.

{% img /images/2014-04-16/4_no_index_in_home_controller.png 'Screenshot of stuff' 'Screenshot of stuff' %}

This is a new error. I need to go into my newly created Home Controller to create my "index" action now.

``` ruby
class HomeController < ApplicationController
  def index
  end
end
```

Let's refresh the page and see what happens.

{% img /images/2014-04-16/5_missing_index_template.png 'Screenshot of stuff' 'Screenshot of stuff' %}

I now need to create an index template. The template name matches the action name. Notice I am using the application to drive how I create things. Way cool.

``` console
touch app/views/home/index.html.erb
```

Let's put something inside of the file as well.

```html
<h1>Yey</h1>
```

Cool! Now, let's create some more routes so I can do more things.

```ruby
Rails.application.routes.draw do
  root 'home#index'

  resources :contacts
end
```

Let's look at all of the routes I just created.

```console
% rake routes

      Prefix Verb   URI Pattern                  Controller#Action
        root GET    /                            home#index
    contacts GET    /contacts(.:format)          contacts#index
             POST   /contacts(.:format)          contacts#create
 new_contact GET    /contacts/new(.:format)      contacts#new
edit_contact GET    /contacts/:id/edit(.:format) contacts#edit
     contact GET    /contacts/:id(.:format)      contacts#show
             PATCH  /contacts/:id(.:format)      contacts#update
             PUT    /contacts/:id(.:format)      contacts#update
             DELETE /contacts/:id(.:format)      contacts#destro
```

Let's throw some more content in index.html.erb. I want to be able to create new data now, so let's throw a "New Contact" link in there as well.
  
```html+erb
  <h1>Yey</h1>

  <%= link_to "New Contact", new_contact_path %>
```
Let's refresh the page and see what happens. Let's ALSO click the "New Contact" link.

{% img /images/2014-04-16/6_no_contacts_controller.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Uh oh! I need to create a Contacts Controller now.

```console
rails generate controller contacts

      create  app/controllers/contacts_controller.rb
      invoke  erb
      create    app/views/contacts
      invoke  test_unit
      create    test/controllers/contacts_controller_test.rb
      invoke  helper
      create    app/helpers/contacts_helper.rb
      invoke    test_unit
      create      test/helpers/contacts_helper_test.rb
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/contacts.js.coffee
      invoke    scss
      create      app/assets/stylesheets/contacts.css.scss
```

Let's refresh the page.

{% img /images/2014-04-16/7_no_new_action_in_contacts_controller.png 'Screenshot of stuff' 'Screenshot of stuff' %}

My controller is created, now I need to create the new actions.

``` ruby
class ContactsController < ApplicationController
  def new
  end
end
```

Cool, let's refresh the page.

{% img /images/2014-04-16/8_missing_new_template.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Now, I need to create a template to match my action name.

``` console
% touch app/views/contacts/new.html.erb
```

Refresh the page and look at a blank screen! Now let's put some stuff inside of it.

``` html+erb
<h1>New Contact</h1>

<%= form_for @contact do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  <br>
  <%= f.submit %>
<% end %>
```

I want to create a new contact, so I put a form in there. Let's fresh the page and see what happens.

{% img /images/2014-04-16/9.png 'Screenshot of stuff' 'Screenshot of stuff' %}

I need to then go create some data to give to my form. I do that inside of the Controller. Let's do that!

``` ruby
class ContactsController < ApplicationController
  def new
    @contact = Contact.new
  end
end
```

Awesome, data is created, let's refresh and see what happens.

{% img /images/2014-04-16/10.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Oh no! I am missing my Model! Let's create one.

``` console
% rails generate model contact
      invoke  active_record
      create    db/migrate/20140416191313_create_contacts.rb
      create    app/models/contact.rb
      invoke    test_unit
      create      test/models/contact_test.rb
      create      test/fixtures/contacts.yml
```

Refresh the page and let's see what happens.

{% img /images/2014-04-16/11.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Oh, I created a Model and I forgot to add data to it so it's telling me to migrate. Let's go fill in the migration.

``` ruby
class CreateContacts < ActiveRecord::Migration
  def change
    create_table :contacts do |t|
      t.string :name
      t.timestamps
    end
  end
end
```

Now, let's run the migration.

``` console
% rake db:migrate

== 20140416191313 CreateContacts: migrating ===================================
-- create_table(:contacts)
   -> 0.0014s
== 20140416191313 CreateContacts: migrated (0.0015s) ==========================
```

Wooo! Got some data fields. Let's fresh the page now:

{% img /images/2014-04-16/12.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Hell yeah. Let's fill in the form and click "Create Contact". 

{% img /images/2014-04-16/13.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Oh no! Let's go create a "new" action inside of our Contacts Controller.

``` ruby
class ContactsController < ApplicationController
  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create params[:contact]
  end
end
```

Cool. Let's go back to the form and fill it out again. Click "Create Contact".

{% img /images/2014-04-16/14.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Oooo. This is a new Rails thing. We need to add a method that whitelists parameters inside of our controller. We do it like this:

``` ruby
class ContactsController < ApplicationController
  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
```

Let's try to submit again.

{% img /images/2014-04-16/15.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Now, I need to either tell my action to render something, or I need to redirect. Let's redirect to our root page.

``` ruby
class ContactsController < ApplicationController
  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
    redirect_to root_path
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
```

Refresh and fill out the form again.

{% img /images/2014-04-16/16.png 'Screenshot of stuff' 'Screenshot of stuff' %}

It redirected correctly, but no data is showing up. Let's render out some data to the user.

``` html+erb
<h1>Yey</h1>

<%= link_to "New Contact", new_contact_path %>
<br>
<% @contacts.each do |contact| %>
  <%= contact.name %>
  <br>
<% end %>
```
Let's refresh the page.

{% img /images/2014-04-16/17.png 'Screenshot of stuff' 'Screenshot of stuff' %}

I forgot to define my @contacts variable! Let's go do that inside of the Home controller.

``` ruby
class HomeController < ApplicationController
  def index
    @contacts = Contact.all
  end
end
```

Let's see what happens when I refresh.

{% img /images/2014-04-16/19.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Oooo data. Let's see what I want to do next:

```console
% rake routes

      Prefix Verb   URI Pattern                  Controller#Action
        root GET    /                            home#index
    contacts GET    /contacts(.:format)          contacts#index
             POST   /contacts(.:format)          contacts#create
 new_contact GET    /contacts/new(.:format)      contacts#new
edit_contact GET    /contacts/:id/edit(.:format) contacts#edit
     contact GET    /contacts/:id(.:format)      contacts#show
             PATCH  /contacts/:id(.:format)      contacts#update
             PUT    /contacts/:id(.:format)      contacts#update
             DELETE /contacts/:id(.:format)      contacts#destro
```

Let's make an "Edit" link next for each contact with the route we found above.

``` html+erb
<h1>Yey</h1>

<%= link_to "New Contact", new_contact_path %>
<br>
<% @contacts.each do |contact| %>
  <%= contact.name %>
  <%= link_to "Edit", edit_contact_path(contact) %>
  <br>
<% end %>
```

Let's refresh and click it.

{% img /images/2014-04-16/20.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Cool. Let's go create that action.

``` ruby
class ContactsController < ApplicationController
  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
    redirect_to root_path
  end

  def edit
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
``` 

Let's refresh and click the "Edit" link again.

{% img /images/2014-04-16/21.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Let's create our "Edit" template now.

``` console
% touch app/views/contacts/edit.html.erb
``` 

And let's populate it with something.

``` html + erb
<h1>Edit Contact</h1>
``` 

Refresh the page.

{% img /images/2014-04-16/22.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Woo woo! Let's put a form in there to edit some data.

``` html+erb
<h1>Edit Contact</h1>

<%= form_for @contact do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  <br>
  <%= f.submit %>
<% end %>
``` 

Refresh and see what happens.

{% img /images/2014-04-16/23.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Now I need to go into my Controller and make that variable.

``` ruby
class ContactsController < ApplicationController
  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
    redirect_to root_path
  end

  def edit
    @contact = Contact.find params[:id]
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
``` 

Refresh and see what happens.

{% img /images/2014-04-16/25.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Let's fill in some data and click the "Update Contact" button.

{% img /images/2014-04-16/26.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Cool! Let's go put that update action in there.

``` ruby
class ContactsController < ApplicationController

  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
    redirect_to root_path
  end

  def edit
    @contact = Contact.find params[:id]
  end

  def update
    @contact = Contact.find params[:id]
    @contact.update_attributes que_params
    redirect_to root_path
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
``` 

And submit the data again.

{% img /images/2014-04-16/27.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Woo woo! Let's see what route we want to do  next

```console
% rake routes

      Prefix Verb   URI Pattern                  Controller#Action
        root GET    /                            home#index
    contacts GET    /contacts(.:format)          contacts#index
             POST   /contacts(.:format)          contacts#create
 new_contact GET    /contacts/new(.:format)      contacts#new
edit_contact GET    /contacts/:id/edit(.:format) contacts#edit
     contact GET    /contacts/:id(.:format)      contacts#show
             PATCH  /contacts/:id(.:format)      contacts#update
             PUT    /contacts/:id(.:format)      contacts#update
             DELETE /contacts/:id(.:format)      contacts#destro
```

Let's have a link that shows each individual contact now:

``` html+erb
<h1>Yey</h1>

<%= link_to "New Contact", new_contact_path %>
<br>
<% @contacts.each do |contact| %>
  <%= link_to contact.name, contact_path(contact) %>
  <%= link_to "Edit", edit_contact_path(contact) %>
  <br>
<% end %>
``` 

Let's click our newly created links.

{% img /images/2014-04-16/28.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Cool. Let's create the show action.

``` ruby
class ContactsController < ApplicationController
  def show
    @contact = Contact.find params[:id]
  end

  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
    redirect_to root_path
  end

  def edit
    @contact = Contact.find params[:id]
  end

  def update
    @contact = Contact.find params[:id]
    @contact.update que_params
    redirect_to root_path
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
``` 

Refresh the page and see what happens.

{% img /images/2014-04-16/29.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Let's go create our template.

``` console
touch app/views/contacts/show.html.erb
``` 

Throw some stuff in there.

``` html+erb
<h1>Show data</h1>

<%= @contact.name %>

<%= link_to "Home", root_path %>
``` 

Let's see what to do next!

```console
% rake routes

      Prefix Verb   URI Pattern                  Controller#Action
        root GET    /                            home#index
    contacts GET    /contacts(.:format)          contacts#index
             POST   /contacts(.:format)          contacts#create
 new_contact GET    /contacts/new(.:format)      contacts#new
edit_contact GET    /contacts/:id/edit(.:format) contacts#edit
     contact GET    /contacts/:id(.:format)      contacts#show
             PATCH  /contacts/:id(.:format)      contacts#update
             PUT    /contacts/:id(.:format)      contacts#update
             DELETE /contacts/:id(.:format)      contacts#destro
```

Let's make a delete link

``` html+erb
<h1>Yey</h1>

<%= link_to "New Contact", new_contact_path %>
<br>
<% @contacts.each do |contact| %>
  <%= link_to contact.name, contact_path(contact) %>
  <%= link_to "Edit", edit_contact_path(contact) %>
  <%= link_to "Delete", contact_path(contact), method: :delete %>
  <br>
<% end %>
``` 

Let's click the link and see what happens.

{% img /images/2014-04-16/30.png 'Screenshot of stuff' 'Screenshot of stuff' %}

Let's make a delete link!

``` ruby
class ContactsController < ApplicationController
  def show
    @contact = Contact.find params[:id]
  end

  def new
    @contact = Contact.new
  end

  def create
    @contact = Contact.create que_params
    redirect_to root_path
  end

  def edit
    @contact = Contact.find params[:id]
  end

  def update
    @contact = Contact.find params[:id]
    @contact.update_attributes que_params
    redirect_to root_path
  end

  def destroy
    @contact = Contact.find params[:id]
    @contact.delete
    redirect_to root_path
  end

private
  def que_params
    params.require(:contact).permit(:name)
  end
end
``` 

All dooooooonnnnnnnnneeee!

{% img /images/2014-04-16/31.png 'Screenshot of stuff' 'Screenshot of stuff' %}

