!SLIDE subsection

## Arel: A Relational Algebra ##

!SLIDE bullets incremental

* Proper SQL generation based
* Generates queries using a proper engine

!SLIDE code

    @@@ ruby
    User.order('attending_changed_at ASC').
    where(:attending => true).to_sql
    # => "SELECT `users`.* FROM `users` WHERE \
    #    (`users`.`attending` = 1) ORDER BY \
    #    attending_changed_at ASC"

!SLIDE

## Or a more complex example... ##
    
!SLIDE code

    @@@ ruby
    photos = Table(:photos)
    users  = Table(:users)
    photo_counts = photos.
      group(photos[:user_id]).
      project(photos[:user_id],
      photos[:id].count)
    users.join(photo_counts).
      on(users[:id].
      eq(photo_counts[:user_id])).to_sql
      
!SLIDE code

    @@@ sql
    SELECT users.*, photos_aggregation.cnt
    FROM users
    LEFT OUTER JOIN (SELECT user_id, count(*)
    as cnt FROM photos GROUP BY user_id)
    AS photos_aggregation
    ON photos_aggregation.user_id = users.id

!SLIDE bullets incremental

* Simpler AR api (less options to first / all / find)
* More effective at generating sql / more complex queries
* No need to write more complex queries by hand
* See http://bit.ly/why-arel