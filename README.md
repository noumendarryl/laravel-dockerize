# Dockerizing Laravel Apps

This is the demo project for my DevOps practice where you'll learn everything you need to know to dockerize Laravel apps.

## About this Project 

This is a standard Laravel v11.20.0 app built following these specifications : 

- PHP 8.3.9
- Laravel 11.20.0

Please follow the instructions below carefully to setup this project on your machine. 

## Setting up the Laravel project

1. **Clone the repository :**

    ```git
    git clone https://github.com/noumendarryl/laravel-dockerize.git
    ```
    
2. **Navigate to the project directory :**

    ```sh
    cd ./laravel-dockerize
    ```

3. **Install the dependencies for the project :**

    ```composer
    composer install
    ```

4. **Copy the example environment files and configure them :**

    ```sh
    cp .env.example .env
    ```

5. **Update your database configuration within the .env file :**

    ```php
	 DB_CONNECTION=<driver>
	 #DB_HOST=127.0.0.1
	 #DB_PORT=<port>
	 #DB_DATABASE=<database>
	 #DB_USERNAME=<username>
	 #DB_PASSWORD=<password>
    ```

6. **Generate application key :**

    ```php
    php artisan key:generate
    ```
    
7. **Test the project :** 
   
    ```php
    php artisan serve
    ```
    
## Running the Docker container

Now that you have successfully set up the project and configured your environment variables, you can dockerize the Laravel project using the following commands:

```sh
# Build the project image
docker build -t <your_image_name> .

# Run the Docker container either using docker run or docker compose command
 docker run -p "8000:80" <your_image_name> -v <any_volume> -d
 or
 docker compose up laravel -d
```

This will start the back-end process at `http://localhost:8000`. If port 8000 is in use on your machine, update the port number in the following files and run the container again :

- .env
- .env.example
