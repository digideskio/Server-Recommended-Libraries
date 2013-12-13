# Third Party Libraries
| Feature | Adopted (recommended) Gem / Library | Experiment / Secondary | Remark |
| ------- | ----------------------------------- | ---------------------- | ------ |
| Amazon Web Service | [aws-sdk](https://github.com/aws/aws-sdk-ruby)
| API Rendering | [rabl](https://github.com/nesquena/rabl) | jbuilder, active_model_serializers
| Authentication | [devise](https://github.com/plataformatec/devise) | [authlogic](https://github.com/binarylogic/authlogic)
| Authorization | [cancan](https://github.com/ryanb/cancan) | [declarative_authorization](https://github.com/stffn/declarative_authorization)
| Best Practice Check | [rails-best-practices](https://github.com/railsbp/rails_best_practices)
| Configuration/Setup | [figaro](https://github.com/laserlemon/figaro)
| Cron scheduling | [whenever](https://github.com/javan/whenever) | [rufus-scheduler](https://github.com/jmettraux/rufus-scheduler)
| CSS | bootstrap-sass
| Database| __postgresql__, mysql <br> redis | sqlite <br> riak
| Debugging | pry, pry-remote, pry-debugger better_errors, binding_of_caller, awesome_print | [debugger](https://github.com/cldwalker/debugger)
| Email | [letter_opener](https://github.com/ryanb/letter_opener): send out email locally <br> [roadie](https://github.com/Mange/roadie): inline css in email to send out
| Facebook | [koala](https://github.com/arsduo/koala) | fb_graph
| File Upload | [paperclip](https://github.com/thoughtbot/paperclip) | carrierwave
| General Cloud | [fog](https://github.com/fog/fog)
| GeoCode | geocoder
| Google Analytic | google-analytics-rails
| Heroku | newrelic_rpm: monitoring <br> airbrake: record error and send email back <br> papertrail: request log <br> redis: redistogo / redisgreen
| HTTP Networking | [rest-client](https://github.com/rest-client/rest-client) | [typhoeus](https://github.com/typhoeus/typhoeus) 
| JSON Parser | oj | yajl-ruby
| OAuth | omniauth, omniauth-facebook, omniauth-google
| Pagination | [will_paginate](https://github.com/mislav/will_paginate) | [kaminari](https://github.com/amatsuda/kaminari)
| Presenter | draper
| Profiler | rack-mini-profiler, miniprofiler
| Push Notification | [urbanairship](https://github.com/groupon/urbanairship)
| Rails   | 4.0.x | 3.2 | 3.x is only for legacy projects
| Ruby    | 2.0.0 | 1.9.3, jruby
| Assets / Javascript / CSS    | [rails-assets](https://rails-assets.org/) | | This will unify the library we use like bower
| Security Check | [brakeman](https://github.com/presidentbeef/brakeman)
| Seed Data | faker
| Setting | [rails-setting-cached](https://github.com/huacnlee/rails-settings-cached)
| Sitemap | sitemap_generator
| Template Engine | haml | slim, erb
| Web Server | unicorn, puma | thin, webrick
| Web SOAP | [savon](http://savonrb.com/version2/)
| Worker  | [sidekiq](https://github.com/mperham/sidekiq), [sidekiq-failures](https://github.com/mhfs/sidekiq-failures)| [resque](https://github.com/resque/resque), [delayed_job](https://github.com/collectiveidea/delayed_job)
