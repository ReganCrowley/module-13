# E-commerce Back End

This is a backend application for an e-commerce site, built using Express.js and Sequelize. It provides a RESTful API to interact with a MySQL database and perform CRUD operations on categories, products, and tags.

To understand the functionality of the application, please watch the [walkthrough video](link-to-video) demonstrating its usage and meeting the acceptance criteria.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [API Routes](#api-routes)
- [Database Models](#database-models)
- [Associations](#associations)
- [Contributing](#contributing)
- [Questions](#questions)
- [License](#license)

## Installation

To install the necessary dependencies, run the following command:

```bash
npm install` 
```

## Usage

1.  Set up your MySQL database and configure the connection details in the environment variable file (`.env`).
2.  Create the database schema using the provided `schema.sql` file in the `db` folder.
3.  Seed the database with test data by running the following command:

`npm run seed` 

4.  Start the server using the following command:

`npm start` 

## API Routes

The following API routes are available:

-   **Categories**
    
    -   `GET /api/categories`: Get all categories
    -   `GET /api/categories/:id`: Get a single category by ID
    -   `POST /api/categories`: Create a new category
    -   `PUT /api/categories/:id`: Update a category by ID
    -   `DELETE /api/categories/:id`: Delete a category by ID
-   **Products**
    
    -   `GET /api/products`: Get all products
    -   `GET /api/products/:id`: Get a single product by ID
    -   `POST /api/products`: Create a new product
    -   `PUT /api/products/:id`: Update a product by ID
    -   `DELETE /api/products/:id`: Delete a product by ID
-   **Tags**
    
    -   `GET /api/tags`: Get all tags
    -   `GET /api/tags/:id`: Get a single tag by ID
    -   `POST /api/tags`: Create a new tag
    -   `PUT /api/tags/:id`: Update a tag by ID
    -   `DELETE /api/tags/:id`: Delete a tag by ID

## Database Models

The application uses the following database models:

-   **Category**
    
    -   `id` (Integer, primary key, auto increment)
    -   `category_name` (String, not null)
-   **Product**
    
    -   `id` (Integer, primary key, auto increment)
    -   `product_name` (String, not null)
    -   `price` (Decimal, not null, decimal value)
    -   `stock` (Integer, not null, default 10)
    -   `category_id` (Integer, references Category's id)
-   **Tag**
    
    -   `id` (Integer, primary key, auto increment)
    -   `tag_name` (String, not null)
-   **ProductTag**
    
    -   `id` (Integer, primary key, auto increment)
    -   `product_id` (Integer, references Product's id)
    -   `tag_id` (Integer, references Tag's id)

## Associations

The following associations are defined between the models:

-   Product belongs to Category (a category can have multiple products, but a product can only belong to one category)
-   Category has many Product models
-   Product belongs to many Tag models (through ProductTag)
-   Tag belongs to many Product models (through ProductTag)

## Contributing

If you would like to contribute to this project, please follow the guidelines below:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix: `git checkout -b feature/your-feature-name` or `git checkout -b bugfix/your-bug-fix`.
3.  Make your changes and commit them with descriptive commit messages.
4.  Push your changes to your forked repository.
5.  Submit a pull request to the main repository.

Please ensure that your code adheres to the project's style guidelines and passes any existing tests. Include a detailed description of the changes you made and any relevant information that would help with the review process.

## Questions

If you have any questions or need further clarification, please feel free to reach out.

## License

This project is licensed under the MIT License

Feel free to modify the content as needed, such as adding your own project-specific information or updating the license details.