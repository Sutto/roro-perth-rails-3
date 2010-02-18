!SLIDE subsection

# ActionMailer #

!SLIDE bullets incremental

* No longer uses tmail
* More controller like interface
* 

!SLIDE

## Instead of... ##

!SLIDE code

    @@@ ruby
    class Notifier < ActionMailer::Base
       def signup_notification(recipient)
         recipients      recipient.email
         subject         "Pirates!"
         from            "system@example.com"
         content_type    "multipart/alternative"
         body            :account => recipient
         part :content_type => "text/html",
           :data => render_message("signup-as-html")
         attachment "application/pdf" do |a|
           a.body = generate_your_pdf_here
         end
         attachment :content_type => "image/jpeg",
           :body => File.read("hi.jpg")
       end
     end
     
!SLIDE

## You can use... ###
     
!SLIDE code
    
    @@@ ruby
    class Notifier < ActionMailer::Base
      default :from => "system@example.com"
      def signup_notification(recipient)
        @account = recipient
        attachments['i.jpg'] = IO.read("hi.jpg")
        attachments['terms.pdf'] = {
          :content => generate_your_pdf_here
        }
        mail(:to => recipient.email,
             :subject => "Ninjas!")
      end
    end
    
!SLIDE code

    @@@ ruby
    Notifier.signup_notification(@user).deliver
    
### was ###

    @@@ ruby
    Notifier.deliver_signup_notification(@user)
    
!SLIDE

## See http://bit.ly/rails-3-mailers ##
