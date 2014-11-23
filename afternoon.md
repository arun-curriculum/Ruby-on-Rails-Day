#Intro to Rails

##Rails from the Rails People

"Ruby on Rails is an open-source web framework that's optimized for programmer happiness and sustainable productivity.

It lets you write beautiful code by favoring convention over configuration."

##What Rails Includes

Rails wraps in a bunch of functionality right out of the box:
- MVC programming pattern convention
- Templating engine with syntax nearly identical to ejs
- ORM called ActiveRecord which is assured to be much better than Sequelize.
- Support for developing APIs with token authentication, namespacing, and multiple response types.
- A database already wrapped in called SQLite3
- An asset pipeline for managing static assets like stylesheets, javascript files, and images.
- Asset "uglifier" or "minifier".
- SASS support
- CoffeeScript support
- Built-in testing suite called MiniTest.
- Authentication flow with Bcrypt and has_secure_password.
- Development web server called WEBrick.
- EASY PEEZY extension of functionality through community-supported gems.
- Oh and sessions... Yeah that's a big one!

##MVC Pattern Coding

####Models
- Models are where data interactions happen.
- You will often see logic related to pulling and saving to databases here.

####Views
- Views are what the users will actually see.
- It is the UI made dynamic through the templating engine.
- Views in Rails are served through layouts.

####Controllers
- Controllers bridge the gap between models and views.
- They take requests and do something with them.
- One controller can have many methods relating to that specific logical concern.

####Routes
- Like Node, routes take HTTP requests from a specific URL and hand them off to a specific controller and a specific method inside that controller.

##Rails Command Line Interface
- Allows you to create new projects.
- You can easily generate new components of your project.
- Easily destroy aspects of your application that you no longer need.
- Three tools we will see a lot:

Rails New:

```
rails new HelloWorld
```

Rails Generate:

```
rails generate controller Hello
```

Rails Destroy:

```
rails destroy controller Hello
```

Rails Console:

```
rails console
```

Rails Server:

```
rails server -p 3000
```

Rails DB:

```
rails db
```

RAKE:

```
rake db:migrate
```

##Hello World in Rails

What it's gonna take:
- A controller with a method
- A route
- A view
- Running server

Let's do it!

##Book Manager
- We will create a simple CRUD app practicing Rails with models.
- Before we implement the frontend UI we will perform the CRUD operations using Rails Console.
- Download the frontend files [here](book_library_html/).

##Asset Pipeline
- Rails wraps in a software called Sprockets that allows you to include multiple static assets in your application.
- Sprockets also handles the SASS and CoffeeScript interpretation as well as the uglifier.
- You can read about Sprockets [here](https://github.com/rails/sprockets-rails).

##Using the Asset Pipeline
- For the basic implementation, all that is needed is for you to place any stylesheets, javascripts, and images in their appropriate folders under app/assets.
- For stylesheets, you can find the asset require code in app/assets/stylesheets/application.css:

```
*= require_tree .
*= require_self
```

- For javascripts, you can find the asset require code in app/assets/javascripts/application.js:

```
//= require turbolinks
//= require_tree .
```

- You will also find a folder called `vendor` at the root of your application. This folder is where you should keep any code written by third parties such as jQuery or Bootstrap.
- To make this work however you will have to alter your application.css and application.js files a bit:

application.css

```
*= require_tree ../../../vendor/assets/stylesheets/
```

application.js

```
//= require_tree ../../../vendor/assets/javascripts/
```