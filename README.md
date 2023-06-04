# Catalog Application

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

The Catalog Application is a web-based catalog management system developed using Spring Boot. It provides a platform for managing products, categories, and user interactions within a catalog. It was built during a DevSuperior course.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## Features

- Product management: Add, view, update, and delete products with detailed information.
- Category management: Organize products into categories for easy navigation and filtering.
- User authentication and authorization: Secure user registration and login with role-based access control.
- Search and filtering: Search products by name, category, or other attributes.

## Prerequisites

Before running the application, make sure you have the following prerequisites installed:

- Java Development Kit (JDK) 17 or later
- Maven
- Postgres or another compatible relational database

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/demoraisnight/SpringBootProj2DSCatalog

2. Set up the database:
   1. Using H2(Some queries doesn't work)
      - Change [application.properties](/application.properties)

        `spring.profiles.active=test`
   2. Using PostgreSQL
      - Change [application.properties](/application.properties)

        `spring.profiles.active=dev`
      - Run POSTGRES container
          ```bash
          sudo docker run -p 5432:5432 --name meu-container-pg12 -e POSTGRES_PASSWORD=1234567 -e POSTGRES_DB=dscatalog postgres:12-alpine
      - Download and Install [pgAdmin4](https://www.pgadmin.org/download/pgadmin-4-apt/)
      - Run [ddl.sql](/src/ddl.sql) on your database
3. Run the project:
   1. Run via Command Line
    ```bash
      mvn package
      java -jar target/some-name.jar
    ```
   2. Running using and IDE
   - [SchoolApplication](/com/example/dscatalog/DscatalogApplication.java)
## Usage
- Register as a user to gain access to the catalog features.
- Explore the product categories and browse through the available products.
- Use the search and filtering options to find specific products.

## Some Endpoints
| Endpoint            | Method | Description               |
|---------------------|--------|---------------------------|
| `/users`            | GET    | Retrieve all users        |                                                                                             |
| `/users/{id}`       | GET    | Retrieve user by ID       |                                                                                            |  
| `/users`            | POST   | Create a new user         | 
| `/users/{id}`       | PUT    | Update user by ID         | 
| `/users/{id}`       | DELETE | Delete user by ID         |                                                                                        |
| `/products`         | GET    | Retrieve all products     |                                                                                             |
| `/products/{id}`    | GET    | Retrieve product by ID    |                                                                                        |  
| `/products`         | POST   | Create a new product      | 
| `/products/{id}`    | PUT    | Update product by ID      |
| `/products/{id}`    | DELETE | Delete product by ID      |   
| `/categories`       | GET    | Retrieve all categories   |                                                                                             |
| `/categories/{id}/` | GET    | Retrieve categories by ID |                                                                                        |  
| `/categories/{id}`  | POST   | Create a new category     | 
| `/categories/{id}`  | PUT    | Update category by ID     |
| `/categories/{id}`  | DELETE | Delete category by ID     |

## Authentication
Some endpoints may require authentication. Include an Authorization header in your request with a valid access token.
`Authorization: Bearer <access_token>`
- You can get your access token at oauth/token using these app credentials
  #### App crendentials
        - client_id:dscatalog
        - client_secret:dscatalog123
  #### User crendentials
        - client_id:maria@gmail.com
        - client_secret:123456
        - grant_type:password
- 
## Technologies Used
- Spring Boot
- Spring Security
- Spring Data JPA
- Spring Validations
- Docker
- PostgreSQL

## Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, please feel free to open an issue or create a pull request. Make sure to follow the existing coding style and commit message conventions.

## License
This project is licensed under the MIT License. See the LICENSE file for details.


