# Approach Paper for Laravel API with PostgreSQL & Keycloak Authentication

## 1. Objective

The goal of this project is to develop a RESTful API using PHP Laravel, with PostgreSQL as the database and Keycloak for authentication and authorization. This API will support CRUD (Create, Read, Update, Delete) operations and will be deployed using Podman on Ubuntu terminal.

## 2. Proposed Solutions

Two possible solutions are considered for this project:

### Approach 1: 
Integrate Laravel API with PostgreSQL and Keycloak, where Keycloak manages user authentication, and the API handles CRUD operations on PostgreSQL.

### Approach 2: 
Use a microservices-based API architecture with Keycloak authentication.

## 3. Approach 1: Laravel API with Keycloak Authentication

### 3.1. Architecture Diagram

_(Provided in the attached diagram)_

### 3.2. Description

#### Solution:
- The client sends a CRUD request to the API.
- Laravel API processes the request and verifies the authentication token with Keycloak.
- If the token is valid, the API performs CRUD operations on PostgreSQL and returns the response.
- If the token is invalid, the API returns an error message.

#### Pros:
- Secure authentication with Keycloak
- Scalable due to microservices architecture
- Easy deployment with Podman containers

#### Cons:
- Complex initial setup due to multiple integrations
- Requires additional resources to manage Keycloak

### 3.3. Implementation Steps

1. **Set Up Laravel Project**
   - Install Laravel on the Ubuntu server.
   - Configure PostgreSQL as the database in the `.env` file.

2. **Set Up Keycloak for Authentication**
   - Deploy Keycloak server and configure clients, and roles.
   - Integrate Laravel with Keycloak using OAuth2/OpenID Connect.
   - Implement token validation in middleware to secure API endpoints.

3. **Develop API Endpoints**
   - Define routes in `routes/api.php` for CRUD operations.
   - Implement controllers for handling requests.
   - Use Eloquent models for database interactions.

4. **Perform CRUD Operations**
   - Allow authenticated users to perform create, read, update, and delete operations.
   - Implement validation and error handling.

5. **Testing & Deployment**
   - Test API functionality using Postman.
   - Deploy the API on an Ubuntu server.
   - Use logs to monitor performance and issues.

### 3.4. Pre-requisites

#### Hardware Requirements
- Minimum 4GB RAM
- Multi-core processor
- At least 20GB storage

#### Software Requirements
- **Operating System:** Ubuntu 22.04 LTS
- **Web Framework:** Laravel 10
- **Database:** PostgreSQL 15
- **Authentication Server:** Keycloak 21
- **Containerization:** Podman
- **PHP Version:** 8.1+

#### Networking Requirements
- Secure API endpoints with HTTPS
- Open ports for PostgreSQL, Keycloak, and API server
- Secure communication between services

## 4. Approach 2: Microservices-Based API with Keycloak Authentication

### 4.1. Architecture Diagram

_(Provided in the attached diagram)_

### 4.2. Description

#### Solution:
1. **Divide the API into Microservices**
   - Separate the API into smaller independent services (e.g., User Management, Product Service, Order Service).

2. **Integrate Keycloak Authentication**
   - Each microservice validates user authentication with Keycloak.
   - Secure endpoints using OAuth2 tokens.

3. **Database Setup and API Communication**
   - Use PostgreSQL as the central database.
   - Each microservice interacts with the database independently.
   - Use API Gateway to manage requests.

4. **CRUD Operations in Microservices**
   - Implement individual controllers for each microservice.
   - Ensure proper validation and response handling.

5. **Testing & Deployment**
   - Test microservices independently.
   - Deploy services in separate containers using Podman/Docker.
   - Monitor API performance and logs.

### 4.3. Pros and Cons

#### Pros:
- Better scalability and maintainability.
- Improved security with isolated services.
- Efficient API performance with independent microservices.

#### Cons:
- More complex setup compared to the monolithic approach.
- Requires careful management of microservices communication.

## 5. Conclusion

After evaluating both approaches, we have chosen **Approach 1: Laravel API with Keycloak Authentication** for the following reasons:

- **Simplicity & Faster Implementation:** Approach 1 provides a structured and traditional method that is easier to implement and manage compared to a microservices-based setup.
- **Security & Authentication:** Keycloak offers a robust and centralized authentication system that seamlessly integrates with Laravel, ensuring secure access control.
- **Performance Efficiency:** A monolithic structure reduces complexity in inter-service communication, making it faster and more efficient for handling API requests.
- **Scalability Considerations:** While microservices offer better scalability in large-scale applications, our current project scope does not require extensive service separation, making Approach 1 more practical.
- **Easier Deployment with Podman:** Managing a single Laravel API container with PostgreSQL and Keycloak simplifies deployment and maintenance compared to handling multiple microservices.
