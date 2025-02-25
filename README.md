# Spring Boot REST API with MySQL

## 📌 Overview
This is a simple REST API built using **Spring Boot** and **MySQL**. It provides CRUD operations for managing users.

## 🛠️ Technologies Used
- **Spring Boot**
- **Spring Data JPA**
- **MySQL**
- **Hibernate**
- **Maven**

---

## 🔧 Setup Instructions

### 1️⃣ Database Setup
**Create MySQL Database:**
```sql
CREATE DATABASE restaurant;
```


### 2️⃣ Configure `application.properties`
Edit `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/restaurant_db
spring.datasource.username=root  # Change if using another user
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
spring.jpa.show-sql=true
```

### 3️⃣ Run the Application
```bash
mvn clean install
mvn spring-boot:run
```

---

## 📌 API Documentation

### 1️⃣ **Create a User**
- **URL:** `POST /api/users`
- **Request Body:**
```json
{
  "name": "John Doe",
  "email": "john.doe@example.com"
}
```
- **cURL Command:**
```bash
curl -X POST http://localhost:8080/api/users \
     -H "Content-Type: application/json" \
     -d '{"name": "John Doe", "email": "john.doe@example.com"}'
```

---

### 2️⃣ **Get All Users**
- **URL:** `GET /api/users`
- **cURL Command:**
```bash
curl -X GET http://localhost:8080/api/users
```

---

### 3️⃣ **Get User by ID**
- **URL:** `GET /api/users/{id}`
- **Example:** `GET /api/users/1`
- **cURL Command:**
```bash
curl -X GET http://localhost:8080/api/users/1
```

---

### 4️⃣ **Update a User**
- **URL:** `PUT /api/users/{id}`
- **Example:** `PUT /api/users/1`
- **Request Body:**
```json
{
  "name": "John Updated",
  "email": "john.updated@example.com"
}
```
- **cURL Command:**
```bash
curl -X PUT http://localhost:8080/api/users/1 \
     -H "Content-Type: application/json" \
     -d '{"name": "John Updated", "email": "john.updated@example.com"}'
```

---

### 5️⃣ **Delete a User**
- **URL:** `DELETE /api/users/{id}`
- **Example:** `DELETE /api/users/1`
- **cURL Command:**
```bash
curl -X DELETE http://localhost:8080/api/users/1
```

---

## 🚀 Future Improvements
- Add **Swagger API Documentation**
- Implement **Authentication & Authorization**
- Add **Unit & Integration Tests**

## 📜 License
This project is **open-source** and available under the [MIT License](LICENSE).

