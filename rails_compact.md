# Rails compact

+ Request->Route->Controller->View
+ Routes defined in config/routes.rb

## Creating new site
    rails new MySite #Creates a new project named MySite
    bundle install #installs needed packages
    rails server #starts WEBRick development webserver

## Creating a simple request/responce cycle
    rails generate model MyItem

    rake db:migrate

    rails generate controller MyItem

In myItem_controller.rb add `home` method:

    def home
    end

In config/routes.rb add route to controller:

    get 'welcome' => 'myItem#home'

In app/views/myItem/home.html.erb add some html code like:

    <h1>Home View</h1>

Open browser with `http://host:port/welcome` and the view should be shown.

## Important Files and Directories
+ `config/routes.rb` route definitions 
+ `app/controllers/` all controllers are stored here. Files are named like `myThing_controller.rb`.
+ `app/views/` all views are stored here. Every controller has its own subdirectory. All actions (methods) defined in controller.rb have a view like `my_action.html.erb` in it.
