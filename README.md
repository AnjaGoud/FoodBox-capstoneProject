# FoodBox-capstoneProject
# FoodBox project
DESCRIPTION

Create a dynamic and responsive online food delivery web application for ordering food items of different cuisines from a restaurant.

Background of the problem statement:
Foodbox is a restaurant chain that delivers food items of different cuisines at affordable prices. It was established in 2014 in Bengaluru, India. It had been serving fine all these years, however, the business analysts noticed a decline in sales since 2016. They found out that the online ordering of food items with companies, such as Swiggy and Foodpanda were gaining more profit by eliminating middlemen from the equation. As a result, the team decided to hire a Full Stack developer to develop an online food delivery web application with a rich and user-friendly interface.
You are hired as the Full Stack Java developer and are asked to develop the web application. The management team has provided you with the requirements and their business model so that you can easily arrange different components of the application.

Features of the application:

Registration
Login
Payment gateway
Searching
Filtering
Sorting
Dynamic data
Responsive and compatible with different devices
Recommended technologies:

Database management: MySQL and Oracle
Backend logic: Java programming, NodeJS
Frontend development: JSP, Angular, Bootstrap, HTML/CSS, and Javascript
Automation and testing technologies: Selenium, Jasmine, and TestNG
DevOps and production technologies: Git, GitHub, Jenkins, Docker, Kubernetes, and AWS
- to connect to the database use localhost:54320 username:foodbox, password: foodbox
- to start phpPgAdmin http://localhost:30000/ username:foodbox, password: foodbox
- To run the application using a remote database on the Heroku host, you need to set the VM options in the startup parameters: -Dspring.profiles.active = heroku
#API
##ItemTypes
- get all item categories by item type id

GET

http://localhost:8080/item-types/{id}/categories

Response:

     {
       [
         {
           "id": 1,
           "name": "category name",
           "description": "some description of category"
         },
         {
           "id": 2,
           "name": "category name",
           "description": null
         }
       ]
     } 

- add new items type    
 
POST

http://localhost:8080/item-types

Request:

     {
      "name": "items type name",
      "description": "items type description",
      "restaurantId": 1
     }
     
Response:
     
     {
      "id": 1,
      "name": "items type name",
      "description": "items type description",
      "restaurantId": 1
     } 
         
##ItemCategory
- get all items from category by category id

GET

http://localhost:8080/item-categories/{id}/items
  
Response:

    {
      [
       {
         "id": 1
         "name": "first item name",
         "description": "string"
        },
       {
         "id": 2
         "name": "second item name",
         "description": "string"
        } 
      ]
    }
    
- add new items category    
 
POST

http://localhost:8080/item-categories

Request:

     {
      "name": "items category name",
      "description": "items category description",
      "itemTypeId": 1
     }
     
Response:
     
     {
      "id": 1,
      "name": "items category name",
      "description": "items category description",
      "itemTypeId": 1
     }     
 
##Item
- get Item by id

GET

http://localhost:8080/item-categories/{id}/items 

Response:

    {
      "id": 1
      "name": "item name",
      "description": "string"
    }
    
##Restaurant
- get restaurant full info by id

GET

http://localhost:8080/restaurants/{id}

Response:

    {
      "id": 1,
      "name": "restaurant name",
      "phoneNumber": "+37529XXXXXXX",
      "description": "some description",
      "photoUrl": null,
      "email": "example@gmail.com",
      "address": {
                   "id": 1,
                   "address": "ÑƒÐ». ÐÐµÐ¸Ð·Ð²ÐµÑÑ‚Ð½Ð°Ñ 60"
                   "city": {
                             "id":1,
                             "name": "ÐœÐ¸Ð½ÑÐº",
                             "country": {
                                          "id": 1,
                                          "name": "Ð‘ÐµÐ»Ð°Ñ€ÑƒÑÑŒ",
                                          "abbreviation": "BY"
                                        }  
                           }
                  }
      "hours": {
                  "regularOpens": 08:00,
                  "regularCloses": 21:00
               }                        
    }
    
- get all restaurant item types by restaurant id with pagination

GET

http://localhost:8080/restaurants/{id}/item-types?start=0&limit=3

Response:

    {
      [
      {
        "id": 1,
        "name": "first item type name",
        "description": "some descriptiom"
      },
      {
        "id": 2,
        "name": "secomd item type name",
        "description": "some descriptiom"
      },
      {
        "id": 3,
        "name": "third item type name",
        "description": null
      },
      ],
      "pageCount": 10
    }    
