# Third Party Libraries
| Feature | Adopted (recommended) Gem / Library | Experiment / Secondary | Remark |
| ------- | ----------------------------------- | ---------------------- | ------ |
| Ruby    | 2.0.0 | 1.9.3, jruby
| Rails   | 4.0.x | 3.2 | 3.x is only for legacy projects
| Database| __postgresql__, mysql <br> redis | sqlite <br> riak
| Worker  | [sidekiq](https://github.com/mperham/sidekiq), [sidekiq-failure](https://github.com/mhfs/sidekiq-failures)| [resque](https://github.com/resque/resque), [delayed_job](https://github.com/collectiveidea/delayed_job)
| HTTP Networking | [rest-client](https://github.com/rest-client/rest-client) | [typhoeus](https://github.com/typhoeus/typhoeus) 
| Web SOAP | [savon](http://savonrb.com/version2/)
| Facebook | [koala](https://github.com/arsduo/koala) | fb_graph
| Debugging | pry, pry-remote, pry-debugger better_errors, binding_of_caller, awesome_print | [debugger](https://github.com/cldwalker/debugger)
| Authentication | [devise](https://github.com/plataformatec/devise) | [authlogic](https://github.com/binarylogic/authlogic)
| Authorization | [cancan](https://github.com/ryanb/cancan) | [declarative_authorization](https://github.com/stffn/declarative_authorization)
| Email | [letter_opener](https://github.com/ryanb/letter_opener): send out email locally <br> [roadie](https://github.com/Mange/roadie): inline css in email to send out
| Pagination | [will_paginate](https://github.com/mislav/will_paginate) | [kaminari](https://github.com/amatsuda/kaminari)
| File Upload | [paper_clip](https://github.com/thoughtbot/paperclip) | carrierwave
| Web Server | unicorn, puma | thin, webrick
| API Rendering | [rabl](https://github.com/nesquena/rabl) | jbuilder, active_model_serializers
| Push Notification | [urbanairship](https://github.com/groupon/urbanairship)
| Template Engine | haml | slim, erb
| Seed Data | faker
| CSS | bootstrap-sass
| JSON Parser | oj | yajl-ruby
| OAuth | omniauth, omniauth-facebook, omniauth-google
| Presenter | draper
| GeoCode | geocoder
| Sitemap | sitemap_generator
| Google Analytic | google-analytics-rails
| Profiler | rack-mini-profiler, miniprofiler
| Heroku | newrelic_rpm: monitoring <br> airbrake: record error and send email back <br> papertrail: request log <br> redis: redistogo / redisgreen
| Amazon Web Service | [aws-sdk](https://github.com/aws/aws-sdk-ruby)
| General Cloud | [fog](https://github.com/fog/fog)
| Configuration/Setup | [figaro](https://github.com/laserlemon/figaro)
| Setting | [rails-setting-cached](https://github.com/huacnlee/rails-settings-cached)
| Security Check | [brakeman](https://github.com/presidentbeef/brakeman)
| Best Practice Check | [rails-best-practices](https://github.com/railsbp/rails_best_practices)
| Cron scheduling | [whenever](https://github.com/javan/whenever) | [rufus-scheduler](https://github.com/jmettraux/rufus-scheduler)
