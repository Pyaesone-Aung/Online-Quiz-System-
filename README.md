# Online Examination System
It is my 4-years project in UCSPyay.
A full-featured Web-based Online Examination System built with Java, Spring Boot, Spring Security, Spring Data JPA, and Thymeleaf. This platform allows administrators to manage exams, questions, and users while providing students with an interactive examination environment and immediate performance reviews.

## Features

### Administrator Module

* **Dashboard Overview:** Monitor key system metrics including total exams, active students, question bank statistics, and exam activity.

* **Exam Management:** Create, update, list, and delete exams. Set time limits, passing scores, and availability dates.

* **Question Bank:** Add and edit multiple-choice questions with customized options and target answers.

* **Student Management:** View and manage registered student accounts and profiles.

* **Result Analytics:** View overall exam results, scores, and individual student submissions.

### Student Module

* **Student Dashboard:** Access upcoming exams, completed tests, and personal performance stats.

* **Interactive Exam Page:** Take exams within a structured online environment complete with a real-time countdown timer (`exam-timer.js`).

* **Instant Result Calculation:** Automatically evaluate submissions upon completion or timer expiration.

* **Detailed Exam Review:** Review completed exams with answer key explanations and detailed score breakdowns.

* **Profile Management:** Manage user account settings and profile information.

## Technology Stack

* **Backend:** Java (JDK 17+), Spring Boot 3.x

* **Security:** Spring Security (Authentication, Role-based Access Control for `ROLE_ADMIN` and `ROLE_STUDENT`)

* **Persistence:** Spring Data JPA, Hibernate

* **Database:** H2 In-Memory Database (Development/Testing), Microsoft SQL Server (Production-ready option)

* **Frontend Template Engine:** Thymeleaf, HTML5, CSS3, JavaScript

* **Build Tool:** Apache Maven

## Project Structure

```
online-exam-system-master/
├── data/                         # Embedded database storage (H2)
├── screenshots/                  # System preview images
│   ├── admindashboard.png
│   ├── adminmanageexam.png
│   ├── adminmanagequestion.png
│   └── exampage.png
├── src/
│   ├── main/
│   │   ├── java/com/example/exam/
│   │   │   ├── config/          # Spring Security & MVC Configuration
│   │   │   ├── controller/      # Admin, Auth, Exam, Student Controllers
│   │   │   ├── model/           # JPA Entities (User, Exam, Question, Result)
│   │   │   ├── repository/      # Spring Data JPA Repositories
│   │   │   └── service/         # Business Logic & User Authentication
│   │   └── resources/
│   │       ├── static/          # JavaScript (timer script), CSS, Images
│   │       ├── templates/       # Thymeleaf HTML Templates (Admin & Student views)
│   │       ├── application.properties
│   │       ├── application-h2.properties
│   │       └── application-sqlserver.properties
│   └── test/                    # Unit and Integration Tests
├── uploads/                     # File/Image uploads directory
├── mvnw / mvnw.cmd              # Maven Wrapper scripts
└── pom.xml                      # Project dependencies & build configuration

```



## Getting Started

### Prerequisites

Ensure you have the following installed on your system:

* **Java Development Kit (JDK):** Version 17 or higher

* **Maven:** Version 3.8+ (or use the included Maven Wrapper `./mvnw`)

* **Git**

### Configuration

Application configurations are specified in `src/main/resources/application.properties`. By default, the application runs using the **H2 database** configuration profile (`application-h2.properties`).

### Build and Run

1. **Clone the repository:**

   ```
   git clone https://github.com/your-username/online-exam-system.git
   cd online-exam-system-master
   
   ```

2. **Build the project using Maven:**

   ```
   ./mvnw clean install
   
   ```

3. **Run the application:**

   ```
   ./mvnw spring-boot:run
   
   ```

4. **Access the application:** Open your browser and navigate to `http://localhost:8080`.

## Database Options

* **H2 Database (Default):**
  Suitable for local development and testing. Data is saved in the local `./data` directory or in-memory.

  * Console Access: `http://localhost:8080/h2-console`

* **SQL Server Configuration:**
  To switch to Microsoft SQL Server for production, update `application.properties`:

  ```
  spring.profiles.active=sqlserver
  
  ```

  Configure your database credentials inside `src/main/resources/application-sqlserver.properties`.

