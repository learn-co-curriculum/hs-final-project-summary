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
4. Emailing capabilites.
5. (Advanced) Database to store data

+ Start wireframing! What is your app going to do? What will your app look like? Come up with plans, and then run them by a teacher to make sure that they are feasible to accomplish in the next few weeks. The [gliffy](www.gliffy.com) app will be helpful for this. Here is a very basic wireframe for the first page of the Albert the Dog story that we storyboarded in class: http://www.gliffy.com/go/publish/6178111. 

### Sinatra Application

Fork and clone the MVC interactive practice lab on Ironboard and follow along with the video below to learn about Model-View-Controller (MVC) frameworks and how to use the Sinatra template we've provided for your own project.

### Sinatra MVC File Structure 

Here is the file structure for your Sinatra project template.

```bash
hs-mvc-interactive-practice
├── models
│   └── sample_model.rb
├── public
│   └── stylesheets
├── views
│   └── index.erb
├── application_controll.rb
├── config.ru
├── Gemfile
└── README.md
```

And here is a break down of what each of those directories and files does. 

#### config.ru

A `config.ru` file is necessary if you are using a deployment tool such as `shotgun` (see `Gemfile`). It specifies to our app handler what files should be run in order to initialize a new server instance of our Sinatra application.

#### `application_controller.rb` file

Our `application_controller.rb` inherits from `Sinatra::Base`, which means it inherits all kinds of functionality from the Sinatra gem. This includes the ability to set up routes that correspond to URLs and display the appropriate HTML/CSS files in the browser. For instance when a user clicks on a link for contact info their browser should show a page with contact info. 

#### `public` directory

The `public` directory holds our front-end assets. In the example above, it holds a `stylesheets` directory where all of our stylesheets are located. Javascript directories and any other front-end assets would be stored in `public` as well.

