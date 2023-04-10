# Coding Challenge
This project is the backend and frontend implementation for coding challenge.
## Description
"coding-challenge-backend" is a rest API that allows you to create, update, and delete users and groups.
and "coding-challenge-frontend" is single page application created by vuejs 3 and typescript.
## Features
- Manage users(CRUD)
- Manage groups(CRUD)
## Technologies Used
- Laravel v10
- Mysql v5.7
- PHP v8.1
- Docker v20.10.21
## Backend Architecture
The project is based on the service repository pattern, which separates the business logic from the data access layer. The service layer interacts with the repository layer to retrieve or store data, and returns the result to the controller. This pattern allows for better separation of concerns and easier unit testing.
## Authentication
The project uses Laravel Passport for OAuth 2 authentication. This provides a secure and scalable authentication system for the API.
## Getting Started
### Prerequisites
- Docker v20.10.21
### Installation
1. Clone the repository. 
    ```
    git clone https://github.com/abdelkarimfares/php-coding-challange.git
    ```
2. Switch to project directory
    ````
    cd php-coding-challange
    ````
3. Clone the backend and frontend repository
    ````
    git clone https://github.com/abdelkarimfares/coding-challange-backend.git
    ````
    ````
    git clone https://github.com/abdelkarimfares/coding-challange-frontend.git
    ````
4. Running docker containers
    ````
    docker-compose up -d
    ````
   By default, the web application is running on http://localhost:8080

5. running laravel migration from terminal
   ````
   docker exec -it laravel bash
   ````
   Then run the migration
   ````
   php artisan migrate
   ````
   Then run database seed
   ````
   php artisan db:seed
   ````
   And Then run the passport installation
   ````
   php artisan passport:install --uuids
   ````
6. Finally, you are done navigate to http://localhost:8080 via the browser.
And the backend will be run on http://localhost:8000



