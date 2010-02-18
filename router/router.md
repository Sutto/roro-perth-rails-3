!SLIDE subsection

# The New Rails Router #

!SLIDE bullets incremental

* More ruby like API
* Rack friendly!
* Has built in backwards compatibility layer
* One of the biggest changes

!SLIDE code

    @@@ ruby
    BarcampPerth::Application.routes.draw do |map|
      match 'signin',
        :to => 'user_sessions#new',
        :as => :signin
      match 'signout',
        :to => 'user_sessions#destroy',
        :as => :signout
      resources :user_session
      match 'signup', :to => 'users#new',
        :as => :signup
      resources :users do
        member do
          post :add_rxp_auth
        end
      end
    end
    
!SLIDE code

## Mount arbitrary rack apps... ##

    @@@ ruby
    BarcampPerth::Application.routes.draw do |map|
      match '/ninjas', :to => YourRackApp
    end
    
!SLIDE

## Lets look at the app... ##