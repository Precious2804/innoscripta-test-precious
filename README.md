# **Project**

NewsAggregator API - A RESTful API for a news aggregator service that pulls articles from various sources and provides endpoints for a frontend application to consume.

---

## **Table of Contents**

1. [Features](#features)
2. [Technologies Used](#technologies-used)
3. [Installation](#installation)
    - [Running with Docker](#running-via-docker)
    - [Running Locally](#running-locally)
4. [Configuration](#configuration)
5. [API Documentation](#api-documentation)
6. [Testing](#testing)
7. [Contact](#contact)

---

## **Features**

-   User authentication (Create Account, Login, Reset Password, Logout).
-   Article Management
-   User Preferences Management
-   Data Aggregation from news sources

---

## **Technologies Used**

-   **Language**: PHP 8.2
-   **Framework**: Laravel 11
-   **Database**: MySQL

---

## **Installation**

### **Running via Docker**

1. Clone the repository:

    ```bash
    git clone https://github.com/Precious2804/innoscripta-test-precious.git
    cd innoscripta-test-precious

    ```

2. Set up .env file

    ```bash
    cp .env.example .env

    ```

3. Update environment variables to match Docker configurations for Database Setup:

    ```bash
    DB_CONNECTION=mysql
    DB_HOST=host.docker.internal
    DB_PORT=db_port
    DB_DATABASE=db_name
    DB_USERNAME=db_user
    DB_PASSWORD=db_pass

    ```

4. Generate Application Key

    ```bash
    php artisan key:generate

    ```

5. Build the Docker containers:

    ```bash
    docker-compose build

    ```

6. Access the Application Container (Run Commands Inside the Container)

    ```bash
    docker-compose exec app bash

    ```

7. Run migrations inside the Docker container

    ```bash
    php artisan migrate

    ```

8. In another terminal, Run the Docker containers:

    ```bash
    docker-compose up -d

    ```

9. Access the application at http://localhost:8000

### **Running Locally**

1. Clone the repository:

    ```bash
    git clone https://github.com/Precious2804/innoscripta-test-precious.git
    cd innoscripta-test-precious

    ```

2. Install Composer Dependencies

    ```bash
    composer install

    ```

3. Set up .env file

    ```bash
    cp .env.example .env

    ```

4. Replace the Database configurations with something like this

    ```bash
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=db_port
    DB_DATABASE=db_name
    DB_USERNAME=db_user
    DB_PASSWORD=db_pass

    ```

5. Generate Application Key

    ```bash
    php artisan key:generate

    ```

6. Run Migrations

    ```bash
    php artisan migrate

    ```

7. Start the local development server

    ```bash
    php artisan serve

    ```

8. Access the application at http://localhost:8000

---

## **Configuration**

-   Update .env file with the required settings:

    -   Database credentials: Set up your database on your prefereed MYSQL host, for instance phpMyAdmin, and update the .env file with your database configuration

    -   API keys: Add the following attributes to your .env files, useful for aggregating data from 3 news sources. You can retrieve the keys via the email submission for this test
        ```bash
        NEWSORG_API_KEY=xxxxxxxxxxxxxxxxxx
        GUARDIAN_API_KEY=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx
        NEW_YORK_TIMES_API_KEY=xxxxxxxxxxxxxxxxxxxxx
        ```

-   Fetch and Store Date from the 3 News Sources above

    -   **NewsApi.org**: to fetch and store articles from NewsAPI.org

        -   Run via Docker
            ```bash
            docker-compose exec app php artisan get:newsorg <category>
            ```
        -   Run Locally
            ```bash
            php artisan get:newsorg <category>
            ```

    -   **The Guardian**: to fetch and store articles from The Guardian

        -   Run via Docker
            ```bash
            docker-compose exec app php artisan get:guardian <category>
            ```
        -   Run Locally
            ```bash
            php artisan get:guardian <category>
            ```

    -   **New York Times**: to fetch and store articles from New York Times
        -   Run via Docker
            ```bash
            docker-compose exec app php artisan get:nytimes <category>
            ```
        -   Run Locally
            ```bash
            php artisan get:nytimes <category>
            ```

Note: <category> is a dynamic value that could be set, and used for fetch from any of the news resources based on a preferred category. For Example, election, entertainment, business etc

---

## **API Documentation**

-   Click the below link access the API Documentation
    https://documenter.getpostman.com/view/15413999/2sAYBRHEyn

---

## **Testing**

-   Run Test with Docker

    ```bash
    docker-compose exec app php artisan test

    ```

-   Run Test Locally
    ```bash
    php artisan test
    ```

---

## **Contact**

-   Email: anipreciousebuka@gmail.com
-   Name: Precious Ani
