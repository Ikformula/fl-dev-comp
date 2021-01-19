

  
## Flutterwave Developer Challenge     
    
This implementation uses the Laravel PHP framework    
    
### Demo Credentials    
 Admin   
**User:** admin@admin.com      
**Password:** secret    
    
### Installation Guide  
This project installs same as a fresh [laravel](laravel.com) app installation  
Download the [jumga.zip](https://github.com/Ikformula/fl-dev-comp/raw/main/jumga.zip) zip file and extract into a folder in your web server. Rename .env.example to .env  
  
**$ composer install**  
  
Set the **APP_URL** environment variable in the .env file

run  
  
**$ php artisan key:generate**  
  to create a new key  
  
Then set the following lines for the database configuration in the .env file.  
  
DB_CONNECTION=mysql    
DB_HOST=127.0.0.1    
DB_PORT=3306    
DB_DATABASE=db_name  
DB_USERNAME=db_user  
DB_PASSWORD=db_password

Then run migration to fill the database with tables

**$ php artisan migrate**  

After that, populate the users table with sample data by running

**$ php artisan db:seed**

Set the other env variables as you see fit


Run the application in your browser by navigating to the url in the **APP_URL** variable

## Explanation:
The app uses flutterwave test environment for development/testing.
Merchants and dispatch riders have to sign up with their bank details which is added to the platform sub accounts on flutterwave via the API endpoint.


Merchants get to apply for a shop, pay and wait for approval.
The platform admin approves the shop by assigning one of the dispatch riders to that shop in the  admin dashboard. (Admin is automatically redirected to the admin dashboard after logging in).


Payments are mostly handled in the App\PaymentsController and App\Service\PaymentService files. Flutterwave payment modal is triggered in the resources/frontend/make-payment.blade.php file.

Uses the following technologies:

 - Laravel PHP Framework
 - MySQL for database
 - Bootstrap UI framework for the views
 - CURL wrapper by [shuber](github.com/shuber)

