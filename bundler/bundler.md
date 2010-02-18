!SLIDE subsection

# The New Bundler #

!SLIDE

## gem install bundler ##

!SLIDE incremental bullets

* Better dependency management
* Solution for gem order issue
* Gemfile which contains a gem manifest
* Not rails specific
* Can be run self contained

!SLIDE code

    @@@ ruby
    source 'http://gemcutter.org'
    gem "rails", "3.0.0.beta"
    gem "haml"
    gem "mysql"
    gem "formtastic"
    gem "rails3-generators"
    gem "rpx_now"
    group :test do
      gem "shoulda"
      gem "factory_girl"
    end

!SLIDE commandline incremental

## Install all gems locally... ##

    $ bundle install vendor/bundler_gems
    
## Or to the system... ##

    $ bundle install

!SLIDE commandline incrememental

## Lock to a specific version of gems ##

    $ bundle lock
    
!SLIDE

## For the most part, it just works. ##

!SLIDE

## Symlink .bundle, vendor/cache and vendor/bundler\_gems w/ capistrano