---
tags: kids, projects
languages: ruby, html, css
---

## Final Project Summary

Here's a recap of what you need to know for your final project:

### Ideation
Your first step is to figure out what you want to build for your final project. At the Flatiron School we love to focus on building things that are *useful* and that make people's lives easier. We'll start from there...

+ Pick a perspective. Who do you want to build for? Your friends? Your mom? Your grandparents? When we 'ideate' we have to have a strong perspective to approach problems from.

+ Ok, now you've chosen your perspective. Write down everything you can think of about this person or group of people. What do they love? What do they hate? What are big (or little) problems that this person faces in their lives?

+ Cool. Pick a problem and start thinking of an app-centric solutions that you might want to build. Here are tools that will be at your disposal:

1. Forms for taking in data from a user.
2. Scraping (pulling data out of existing websites)
3. Text messaging capabilities.
4. Emailing capabilities.
5. (Advanced) Database to store data

+ Start wireframing! What is your app going to do? What will your app look like? Come up with plans, and then run them by a teacher to make sure that they are feasible to accomplish in the next few weeks. The [gliffy](www.gliffy.com) app will be helpful for this. Here is a very basic wireframe for the first page of the Albert the Dog story that we storyboarded in class: http://www.gliffy.com/go/publish/6178111. 

### Sinatra Application

We will be using the Sinatra web framework to create web applications. Fork and clone the MVC interactive practice lab on Ironboard and follow along with this video

https://vimeo.com/112848433

to learn about Model-View-Controller (MVC) frameworks and how to use the Sinatra template we've provided for your own project. There is a `master` branch with a blank template and there is also completed project code in the `complete` branch. (You may want to pull the `goat.rb` code from this `complete` branch.)

Once you've finished following along with the video you'll be ready to add some embedded ruby to your views to display instances of your goat class. 

We want to display our goat in the goat view, so we'll need to create the instance of our goat within the `/goat` route like so:

```ruby
  get '/goat' do
    @goat1 = Goat.new("Callie",7)
    erb :goat
  end
```

Notice that we are storing this goat in an instance variable `@goat1`. We need to use an instance variable (and not a local variable) so that this goat is available outside of the `get '/goat'` method and can be displayed in the goat.erb view.

We use erb tags to display embedded ruby in our erb templates. Erb tags looks like this `<%= %>`. So if we want to display the name of `@goat1` in our goat view we would add the following code to the goat.erb template:

```erb
<body>
  <h1>Even MORE Fun With Goats</h1>
  <p>Name: <%= @goat1.name %></p>
</body>
```
Try adding the goat's name, age, pokes and milk in udder to your template.

There is just one more step we need to take before we will be able to see our new goats in the browser, we need to make sure that the code in our `application_controller.rb` file has access to the code in our goat model. To do this, we need to require the `goat.rb` file by adding the following line of code to the top of our `application_controller.rb` file:

```ruby
require_relative './models/goat.rb'
```

Now you can create as many instances of the goat as you want in the application controller. Boot up your server with the shotgun command in the terminal and take a look at your goats!

### Sinatra MVC File Structure 

For your reference, here is the file structure for your Sinatra project template and a quick summary of what each of those directories and files does. 

```bash
hs-mvc-interactive-practice
├── models
│   └── sample_model.rb
├── public
│   └── stylesheets
├── views
│   └── index.erb
├── application_controller.rb
├── config.ru
├── Gemfile
└── README.md
```

### `models` directory

This folder holds the logic behind your program. If you were building facebook you would save your user.rb file with a User class in this directory.

#### `public` directory

The `public` directory holds our front-end assets. In the example above, it holds a `stylesheets` directory where all of our stylesheets are located. Javascript directories and any other front-end assets (like image files) would be stored in `public` as well.

### `views` directory
In a Sinatra app we use .erb files instead of .html files because .erb files allow us to include regular, old HTML tags AND special erb tags which contain Ruby code. 

#### `application_controller.rb` file

Our `application_controller.rb` inherits from `Sinatra::Base`, which means it inherits all kinds of functionality from the Sinatra gem. This includes the ability to set up routes that correspond to URLs and to display the appropriate .erb files (with HTML/CSS and embedded Ruby) in the browser. 

#### `config.ru` file

A `config.ru` file is necessary if you are using a deployment tool such as `shotgun` (see `Gemfile`). It specifies to our app handler what files should be run in order to initialize a new instance of our Sinatra application.

#### `Gemfile`

This holds a list of all the gems needed to run the application. For example, we need the `shotgun` gem to get a server started on our computer. All of the gems in a Gemfile can be downloaded by running the command `bundle install` from our terminal.





