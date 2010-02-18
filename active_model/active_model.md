!SLIDE subsection

# ActiveModel #

!SLIDE bullets incremental

* Extracted out non-SQL parts of active record
* Can be used in any library (validations, etc)
* Doesn't require rails
* Very modular

!SLIDE code

    @@@ ruby
    class Person
      include ActiveModel::Validations
      attr_accessor :first_name
      validates_each :first_name do |record, attr, value|
        record.errors.add attr, 'starts with z.' if value.to_s[0] == ?z
      end
    end
    person = Person.new(:first_name => 'zoolander')
    person.valid? #=> false
     
!SLIDE

## All the cool bits of AR, Not of the DB requirements ##
## Makes writing other ORMs much easier ##

!SLIDE bullets incremental

* Callbacks
* Serialization
* Attribute Methods
* Validation
* Change Tracking
* Observers

!SLIDE

## http://github.com/rails/rails/tree/master/activemodel/ ##
