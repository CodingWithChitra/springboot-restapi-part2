# springboot-restapi-part2
# 📚 Library Management REST API

This project is a simple RESTful API built with Spring Boot to manage a basic library system. It demonstrates CRUD operations for books and members, as well as borrowing and returning functionality.

---

## 🚀 Features

- 📘 CRUD for **Books**
- 👤 CRUD for **Members**
- 🔄 **Borrow** and **Return** books
- 📦 Spring Data JPA + H2 (in-memory) or PostgreSQL
- 🔐 Basic Authentication

---

## 🛠️ Tech Stack

- Java 17+
- Spring Boot 3+
- Spring Data JPA
- Spring Web
- Spring Security (Basic Auth)
- PostgreSQL / H2
- Lombok (optional)

---

## 📁 Project Structure

```text
src/
├── main/
│   ├── java/com/example/library/
│   │   ├── controller/
│   │   ├── entity/
│   │   ├── repository/
│   │   └── LibraryApplication.java
│   └── resources/
│       ├── application.properties
├── test/
```

---

## 🔌 Endpoints

### 📘 Books
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/books` | Add a new book |
| GET | `/books` | Get all books |
| GET | `/books/{id}` | Get book by ID |
| PUT | `/books/{id}` | Update book |
| DELETE | `/books/{id}` | Delete book |

### 👤 Members
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/members` | Add a new member |
| GET | `/members` | Get all members |
| GET | `/members/{id}` | Get member by ID |
| PUT | `/members/{id}` | Update member |
| DELETE | `/members/{id}` | Delete member |

### 🔄 Borrow & Return
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/borrow?memberId=X&bookId=Y` | Borrow a book |
| PUT | `/return/{id}` | Return a book |

---

## 🔐 Basic Auth

- Default username/password: `user` / generated on startup (or override in `application.properties`).

```properties
spring.security.user.name=admin
spring.security.user.password=admin123
```

---

## 🧪 Test with Postman

1. Set Basic Auth credentials.
2. Use the endpoints listed above.
3. Set headers: `Content-Type: application/json`
4. Test POST with sample body:
```json
{
  "title": "Spring Boot in Action",
  "author": "Craig Walls",
  "isbn": "1234567890"
}
```

---

## 🛠️ Gradle Build (build.gradle)

```groovy
plugins {
    id 'org.springframework.boot' version '3.2.0'
    id 'io.spring.dependency-management' version '1.1.0'
    id 'java'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '17'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web'
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
    implementation 'org.springframework.boot:spring-boot-starter-security'
    runtimeOnly 'com.h2database:h2'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```

Run the app:
```bash
./gradlew bootRun
```

Build the app:
```bash
./gradlew build
```

---

## 🌐 Connect to H2 Console
- URL: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:testdb`
- User: `sa`, Password: (blank)

---

## 📦 Run with Docker *(Optional)*
> Coming soon...

---

## 🤝 Contributions
PRs are welcome!

---

## 📄 License
MIT License

