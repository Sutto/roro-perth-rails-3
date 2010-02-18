!SLIDE subsection

# Other Cool Features #

!SLIDE

## Generators using Thor ##
### http://github.com/indirect/rails3-generators ###

!SLIDE

## UJS (Use prototype / jquery with helpers) ##

!SLIDE

## HTML5-friendly ##

!SLIDE

## Component Agnostic ##

!SLIDE bullets incremental

* ORM (AR, DM)
* Test Framework (T::U, Rspec)
* Fixtures (built in, FactoryGirl)
* Template Framework (ERB, Haml)

!SLIDE

## Auto HTML escaping ##

!SLIDE

## Better Plugin API ##

!SLIDE bullets incremental

* plugin, engine, app distinction
* Public / documentated api
* Hook into arbitrary things
* Namespaced applications

!SLIDE

## named\_scope changes ##

!SLIDE

## scripts/rails ##

!SLIDE

## Responders ##

!SLIDE code

    @@@ ruby
    class PeopleController < ApplicationController
      respond_to :html, :xml, :json
      def index
        @people = Person.find(:all)
        respond_with(@people)
      end
    end

!SLIDE

## RAILS\_ROOT is deprecated. ##

!SLIDE

## http://guides.rails.info/3\_0\_release_notes.html ##

!SLIDE

# Upgrading #

!SLIDE center

![Questions?](lolcats-funny-pictures-questionmark.jpg)

!SLIDE

## http://roro-perth-rails3.heroku.com/ ##