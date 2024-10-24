# Rule Engine AST

## Overview
Access the site here:- https://ruleengineast-frontend.onrender.com/

The **Rule Engine AST** is a backend application designed to manage and evaluate complex business rules using an Abstract Syntax Tree (AST) approach. The system supports CRUD operations for rules stored in a database, making it easy to create, update, and delete rules dynamically. This project leverages **Java**, **Spring Boot**, and **MongoDB** for efficient rule management and execution.

## Features

- **Dynamic Rule Management**: Add, update, delete, and retrieve business rules.
- **Abstract Syntax Tree (AST) Parsing**: Rules are parsed using an AST structure for optimized evaluation.
- **Database Integration**: Uses MongoDB to store rules.
- **RESTful API**: Provides endpoints to manage rules.
- **Error Handling**: Robust validation and error management for rule parsing and evaluation.
- **Performance Optimization**: Efficient rule evaluation leveraging AST.

## Project Structure

```
├── src
│   ├── main
│   │   ├── java
│   │   │   └── org.example.ruleengine
│   │   │       ├── config              # Configuration files
│   │   │       ├── controller          # REST API Controllers
│   │   │       ├── model               # Domain models and data classes
│   │   │       ├── repository          # Repository interfaces for MongoDB
│   │   │       └── service             # Business logic and rule evaluation
│   │   └── resources
│   │       ├── application.properties  # Configuration settings
│   │       └── static                  # Static assets (if any)
│   └── test
│       └── java
│           └── org.example.ruleengine  # Unit tests and integration tests
├── build.gradle                        # Project dependencies and build settings
└── README.md                           # Project documentation
```

## Requirements

- **Java 19**
- **Gradle** (for build and dependency management)
- **MongoDB** (Database)
- **Spring Boot** 3.x
- **Docker** (Optional for containerization)

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/RuleEngineAST.git
   cd RuleEngineAST
   ```

2. **Set up MongoDB**:
   - Ensure MongoDB is installed and running on your local machine or use a cloud database like MongoDB Atlas.
   - Create a database named `ruleengine_db` and a collection named `rules`.

3. **Configure application.properties**:
   - Update the `application.properties` file with your MongoDB credentials.
   
   Example:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/ruleengineast
   spring.datasource.username=root
   spring.datasource.password=admin
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
   spring.jpa.hibernate.ddl-auto=update
   ```

4. **Build the project**:
   ```bash
   ./gradlew build
   ```

5. **Run the application**:
   ```bash
   ./gradlew bootRun
   ```

## API Endpoints

| Method | Endpoint              | Description                                |
|--------|-----------------------|--------------------------------------------|
| GET    | `/api/rules`           | Retrieve all rules                         |
| GET    | `/api/rules/{id}`      | Retrieve a rule by ID                      |
| POST   | `/api/rules`           | Add a new rule                             |
| PUT    | `/api/rules/{id}`      | Update an existing rule                    |
| DELETE | `/api/rules/{id}`      | Delete a rule by ID                        |
| POST   | `/api/rules/evaluate`  | Evaluate a rule with provided input data   |

## Rule Structure

Rules are stored in a JSON-like format in MongoDB. A typical rule structure looks like this:

```json
{
  "id": "unique_rule_id",
  "name": "Sample Rule",
  "description": "This rule checks if the value exceeds the threshold.",
  "conditions": [
    {
      "field": "temperature",
      "operator": ">",
      "value": 30
    }
  ],
  "actions": [
    {
      "field": "status",
      "action": "set",
      "value": "alert"
    }
  ]
}
```

## Usage

1. **Add a new rule**:
   - Use a POST request to `/api/rules` with the JSON rule structure.
   
2. **Evaluate a rule**:
   - Use the endpoint `/api/rules/evaluate` to evaluate a rule against sample data.

## Access

You can access the frontend of the Rule Engine AST project, deployed on **Render**, at:

**[Rule Engine AST - Frontend](https://ruleengineast-frontend.onrender.com/)**

Feel free to explore the rule management and evaluation features directly through the web interface.

## Testing

Run the test suite using Gradle:
```bash
./gradlew test
```

## Deployment

1. **Docker**:
   - Build the Docker image:
     ```bash
     docker build -t rule-engine-ast .
     ```
   - Run the Docker container:
     ```bash
     docker run -p 8080:8080 rule-engine-ast
     ```

2. **Render Deployment**:
   - The application is deployed on [Render](https://render.com/), allowing for seamless hosting and scaling.

## Contributing

Feel free to submit issues, fork the repository, and send pull requests. Contributions are welcome!

## License

This project is licensed under the MIT License.

## Contact

For any questions or support, please contact **Lavish Vaishnav** at [vaishnavlavish27@gmail.com](mailto:vaishnavlavish27@gmail.com).

--- 

