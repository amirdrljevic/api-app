# README - JWT Token

An example of Token-based Authentication (also known as JSON Web Token authentication) 

For this you need following gems:
* gem 'pg', '~> 1.2', '>= 1.2.3'  
* gem 'bcrypt', '~> 3.1', '>= 3.1.16'
* gem 'jwt', '~> 2.3'
* gem 'simple_command', '~> 0.1.0'

You also need to create some resource to be requested as a test. Run this command to create a resource from top to bottom:
rails g scaffold Item name:string description:text
rails db:migrate

After this, run the console:
rails c

* Create some Item:
Item.create!(name: 'Laptop', description: 'A fun toy')

* Create a user
User.create!(email: 'example@mail.com' , password: '123123123' , password_confirmation: '123123123')

* curl -H "Content-Type: application/json" -X POST -d '{"email":"example@mail.com","password":"123123123"}' http://localhost:3000/authenticate

* Your token will now be returned, an example:
{"auth_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJleHAiOjE0NjA2NTgxODZ9.xsSwcPC22IR71OBv6bU_OGCSyfE89DvEzWfDU0iybMA"}

* Copy the token you got returned 

* Insert that token in this curl request:
curl -H "Authorization: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJleHAiOjE0NjA2NTgxODZ9.xsSwcPC22IR71OBv6bU_OGCSyfE89DvEzWfDU0iybMA" http://localhost:3000/items

* With the token prepended, you will get an array ([]) returned

