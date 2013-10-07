# Why this is required ?
The objective of this document is to reach consensus of coding convention, useful gems and standard libraries that we (server team) use everyday. The reason is that once we ALL are familiar with the adopted libraries, we can help/cover each other. The list will be kept update-to-date with the latest version of library. Therefore, if you want to do some feature X, you should look for the recommended gems described below. The list is not complete, and thus please help fill out where necessary. Please also link to github too

## Table of Contents
* [Language Coding Conventions](https://github.com/nlds90/Server-Library-Standardization/blob/master/LANGUAGE_CODING_CONVENTIONS.md)  
* [Project Technical Conventions](#project-technical-conventions)  
* [Project Structure](#project-structure)  
* [Third Party Libraries](#https://github.com/nlds90/Server-Library-Standardization/blob/master/THIRD_PARTY_LIBRARIES.md)  
* [Server Setup Checklist](#server-setup-checklist)  
* [Production Environment](#production-environment)  
* [Reference](#reference)  

### Project Technical Conventions
* You should use rvm, with latest rails and stable ruby version   
* Use git for version control system, follow git workflow  
* Use github to store application 
* Use Heroku for deployment 
 
### Project Structure
* __app__ : organizes your application components(include controllers, assets, helpers, models, views, ...)
  * __controllers__ : controller classes handle web request
  * __models__ : classes which model and wrap data stored in our application's database (backend business logic)
      * __concerns__ : classes which build modules intended for mixins, useful to refactor fat model **[view more](http://engineering.appfolio.com/2013/06/17/ruby-mixins-activesupportconcern/)** 
  * __helpers__ : classes which has any helper methods to assist views and controllers
  * __views__ : all templates which we use to fill in with data to render for clients
      * __layouts__ : template files which use to layout applications.(Common use: header, footer, ...)
  * __mailers__ : classes which use to deliver email
  * __assets__ : images, javascript, css
  * __workers__ : classes which perform background task (sidekiq, resque, ...)
  * __presenters__ : classes which use to remove logic in view
  * __decorators__ : same as presenters
  * __sweepers__ : expire cache(ActionController::Caching::Sweeper)
* __bin__ : contains the rails script that starts your app and can contain other scripts you use to deploy or run through your application
* __config__ : configure your application's runtime rules, routes, database, and more
  * __environments__ : default rails app has 3 environments : production , development and test ( if you want more environments , you should put it in here)
  * __initializers__ : After loading the framework and any gems in your application, Rails turns to loading initializers , you can use initializers to hold configuration settings
  * __locales__ : implement Rails internationalization (i18n) (multiple languages)
  * __database.yml__ : this file contains database configuration of all environments
  * __routes.rb__ : this file contains all routes of your application
* __db__ : all the migration files of application , schema , seeds file to create dump data
* __lib__ : put all your own libraries , tasks ,assets here
  * After all of your gems are loaded and your application is up Rails will append lib/ directory to your load path. Any files you put in there can now be required the exact same way gems are
  * Any code that you feel needs to go into an initializer and has nothing to do with actually setting preferences or something of that manner almost always should go into the lib/ directory
  * Using lib/ to extend core, stdlib, or a gem
  * Using lib/ as a pattern to extracting Rubygems
* __log__ : contain all server logs
* __public__ : contain all static files that always serve to users
* __spec__ : rspec framework to integrate test

### Server Setup Checklist

##### AWS
    1. Are you not the only one who has access to this server?
    2. Keep a copy of AWS vm keypair (ec2) with PM at least
    3. Open necessary ports only (22, 80)
    
##### Heroku
    1. Ownership of app (heroku) should belong to company’s account
    2. Set your default app to staging (for heroku)
        a. git remote add staging git@heroku.com:<your-app-here>-staging.git
        b. git remote add production git@heroku.com:<your-app-here>.git
        c. git config heroku.remote staging
    3. Check your environment/app when you do migration
