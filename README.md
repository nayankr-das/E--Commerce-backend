## E-Commerce Backend (Spring Boot)

This is a simple Java-based e-commerce backend application built with Spring Boot, JSP, Spring Security, and Hibernate. It supports admin and user workflows, including product management, user registration, login, and shopping cart features.

### Features
- Admin and user roles
- Product, category, and user management
- Secure authentication and authorization
- MySQL database integration

### Getting Started
1. Clone the repository
2. Configure your database settings in `src/main/resources/application.properties`
3. Build and run the project using Maven:
   ```bash
   mvn clean package
   mvn spring-boot:run
   ```
4. Access the app at [http://localhost:8080/](http://localhost:8080/)

---

#### Author & Contributor

- [NAYAN KUMAR DAS](https://github.com/nayan-code)

---

© 2026 Nayan

### 2) Configure database

Update `src/main/resources/application.properties`:

```properties
db.driver=com.mysql.cj.jdbc.Driver
db.url=jdbc:mysql://localhost:3306/ecommjava?createDatabaseIfNotExist=true
db.username=your_db_user
db.password=your_db_password

hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
hibernate.show_sql=true
hibernate.hbm2ddl.auto=update
entitymanager.packagesToScan=com
```

### 3) Optional: seed sample data

Run `basedata.sql` against your database if you want initial categories/users/products.

Note: sample credentials in `basedata.sql` are development-only defaults.

### 4) Run the app

```bash
mvn clean package
mvn spring-boot:run
```

App URL: http://localhost:8080/

## IDE Notes (IntelliJ)

If JSP views are not resolved, set the run configuration working directory to `$MODULE_WORKING_DIR$`.

## Core Endpoints

### Public/User

- `/`
- `/login`
- `/register`
- `/newuserregister`
- `/user/products`
- `/profileDisplay`

### Admin

- `/admin/`
- `/admin/Dashboard`
- `/admin/products`
- `/admin/categories`
- `/admin/customers`

## Security Model

- Admin routes under `/admin/**` require role `ADMIN`
- User routes require role `USER`
- Login pages:
  - Admin: `/admin/login`
  - User: `/login`
- CSRF protection is enabled for form submissions

## Build and Test

```bash
mvn clean verify
```

Notes:

- `mvn test` requires a reachable database because context startup initializes Hibernate and datasource beans.

## CI/CD

A Jenkins pipeline is included in `jenkins file` with stages for:

- Checkout
- Build
- Test
- Deploy (template placeholder)

Adjust branch, deployment steps, and credentials for your environment.

## Troubleshooting

- `Could not resolve placeholder 'db.driver'`:
  - Ensure all `db.*` keys exist in `application.properties`
- JSP pages not rendering:
  - Verify working directory and `spring.mvc.view.prefix=/views/`
- Tests failing on startup:
  - Start MySQL and verify connection credentials first

## Screenshots

![Preview 1](https://github.com/jaygajera17/E-commerce-project-springBoot/assets/81226571/02a04d3c-1fc9-418c-b231-639f6525d07e)
![Preview 2](https://github.com/jaygajera17/E-commerce-project-springBoot/assets/81226571/24c4451b-43a6-4c23-a78a-786eab4303b0)
![Preview 3](https://github.com/jaygajera17/E-commerce-project-springBoot/assets/81226571/93c1baeb-326c-450f-867e-a883900a6644)



Current priorities:

- Solid foundation: CI, Docker Compose, contribution workflow, and test coverage.
- Complete e-commerce domain: cart, checkout, auth, search, and API docs.
- Industry patterns: caching, concurrency control, observability, and scalability.
- Long-term architecture: event-driven patterns and microservice decomposition guide.



## ⭐ Support This Project

If this project helped you, please consider giving it a star on GitHub.
Your support helps improve visibility and motivates future maintenance.



<div align="center">
  <sub>Built as a college project · Grown into a community resource · Maintained with ❤️</sub>
</div>
