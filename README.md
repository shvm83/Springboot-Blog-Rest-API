# Springboot-Blog-Rest-API
This project is a robust, full-featured Blog RESTful API built with Spring Boot. It's designed to manage a complete blogging platform, offering core functionalities like CRUD operations for posts, categories, and comments, and securing the API using Role-Based Access Control (RBAC) with JSON Web Tokens (JWT).

Key Features and Functionalities
1. Core Blog Management (CRUD)
The API supports comprehensive management of blog content:
 * Post Management: Full CRUD (Create, Read, Update, Delete) functionality for blog posts.
 * Comment Management: Allows users to create, view, update, and delete comments associated with specific posts.
 * Category Management: Implements CRUD operations for organizing posts into categories, enabling the Category Management Feature.
2. Role-Based Authentication and Authorization
A key feature is the secure, multi-level access control:
 * JWT Security: Uses JSON Web Tokens (JWT) for stateless, secure authentication.
   * JwtTokenProvider.java handles token generation and validation.
   * JwtAuthenticationEntryPoint.java and JwtAuthenticationFilter.java manage the authentication flow.
 * Role-Based Access Control (RBAC): Access to certain endpoints (like creating, updating, or deleting posts/categories) is restricted based on the user's assigned Role (Role.java entity).
 * Custom User Details: CustomUserDetailsService.java provides the core logic for loading user-specific authentication and authorization data.
 * Authentication Endpoints: Dedicated endpoints (AuthController.java) for user Login and Registration.
3. Layered Architecture
The project adheres to the best practices of a three-layer architecture:
 * Controller Layer (controller package): Exposes the RESTful endpoints for the API (PostController.java, CategoryController.java, etc.).
 * Service Layer (service package): Contains the business logic and transaction management. This layer defines the contracts (PostService.java, CategoryService.java) and their concrete implementations (PostServiceImpl.java, CategoryServiceImpl.java).
 * Repository Layer (repository package): Handles data persistence operations, extending Spring Data JPA interfaces (PostRepository.java, CategoryRepository.java, UserRepository.java).
4. Robust Exception Handling
The API ensures predictable and informative error responses:
 * Global Exception Handling: GlobalExceptionHandler.java centralizes exception handling across all controllers.
 * Custom Exceptions: Uses specific exception classes like BlogAPIException.java and ResourceNotFoundException.java to convey precise error information to the client.

Project Structure Highlights
The project is structured logically into well-defined packages:
 * controller: REST API endpoints.
 * entity: JPA Entities (User, Post, Category, Role, Comment).
 * payload: Data Transfer Objects (DTOs) for request/response bodies (PostDto, CategoryDto, LoginDto, RegisterDto, etc.).
 * repository: Data access interfaces.
 * service: Business logic interfaces and implementations (impl).
 * security: Core security components (JWT filter, token provider, user details service).
 * exception: Custom exception classes and the global handler.
 * utils: Utility classes (AppConstants, PasswordEncoderGenerator).

 Technology Stack
| Component | Technology / Framework |
| Backend Framework | Spring Boot |
| Data Persistence | Spring Data JPA (Hibernate) |
| Security | Spring Security with JWT |
| Database | Configurable via application.properties |
| Build Tool | Maven |
| Language | Java |
