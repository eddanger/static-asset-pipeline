Static Asset Pipeline
=====================

Now your static CSS and Javascript pages can have the power of Sprockets!

Just a simple rake task and some choice gems and you can have the
structure of the Rails Asset Pipeline without the Rails.

## Structure your assets

```
├── Gemfile
├── Gemfile.lock
├── Rakefile
├── assets
│   ├── javascripts
│   │   └── application.js
│   │   └── friday.js.coffee
│   ├── stylesheets
│   │   └── application.css
│   │   └── hello.css.less
├── public
│   ├── css
│   │   └── application.js
│   ├── js
│   │   └── application.js
```

## Bundle your Gems

`bundle install`

## Compile your assets

`rake assets:compile`


## Rejoice!

Your compiled assets will be in your `/public` folder ready to do your bidding...

