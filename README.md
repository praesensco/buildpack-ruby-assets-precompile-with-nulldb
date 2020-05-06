Heroku buildpack for running assets compilation with [nulldb](https://github.com/nulldb/nulldb) adapter.
======================

This buildpack is intended for use after the regular [ruby-buildpack](https://github.com/heroku/heroku-buildpack-ruby). 

When precompiling assets, Rails attempts to connect to DB. If it's not possible to connect to DB during Heroku `build` phase it fails. A workaround is to use [nulldb](https://github.com/nulldb/nulldb) as the database adapter during asset precompilation:

```
$ bundle exec rake assets:precompile DB_ADAPTER=nulldb
```
# Usage

Add the buildpack-ruby-assets-precompile-with-nulldb to your buildpack list:

```
$ heroku buildpacks:add https://github.com/praesensco/buildpack-ruby-assets-precompile-with-nulldb.git
```
