# Infocuor — Photography & Event Booking Platform

![Java](https://img.shields.io/badge/Java-17-ED8B00?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.1-6DB33F?logo=springboot&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb&logoColor=white)
![AWS S3](https://img.shields.io/badge/AWS-S3-569A31?logo=amazons3&logoColor=white)

A complete full-stack event management and photography booking platform consisting of a **Spring Boot** REST API, a **React + Tailwind CSS** client portal, and a **React + Material UI** admin dashboard. Built to streamline photography event listings, session reservations, bank transfer slip verification, and post-production photo progress tracking.

---

## Key Features

### Client Portal (`Frontend/`)
- **Event & Session Discovery**: Browse upcoming photography events, indoor/outdoor session types, pricing packages, and available timeslots.
- **Online Booking & Payment Slip Upload**: Reserve sessions online and securely upload bank transfer receipts directly to **AWS S3**.
- **Booking & Photo Progress Tracker**: Monitor booking approval status and post-shoot editing/delivery milestones in real time.
- **Client Account Management**: Registration, JWT/session login, profile editing, and OTP-based email password reset.

### Admin Dashboard (`Admin/`)
- **Events, Packages & Sessions CRUD**: Create and manage photography events, packages, and daily timeslot availability.
- **Booking & Payment Verification**: Review incoming client reservations, inspect uploaded payment slips, and update studio bank/contact details.
- **Post-Production Progress Workflow**: Update photo editing and delivery status per booking.
- **Portfolio Showcase Management**: Curate and update featured photography galleries.

---

## Tech Stack

| Module | Technologies |
| :--- | :--- |
| **Backend (`Backend/`)** | Java 17, Spring Boot 3.4.1, Spring Security, Spring Data MongoDB, AWS S3 SDK, JavaMail |
| **Client Frontend (`Frontend/`)** | React 19, Vite, Tailwind CSS v4, Framer Motion, React Router v7, Axios |
| **Admin Portal (`Admin/`)** | React 19, Vite, Material UI (MUI v7), Tailwind CSS v4, Date-fns, Lucide Icons |
| **Database & Storage** | MongoDB, AWS S3 (`ap-south-1`) |

---

## Project Structure

```text
Infocur-site-main/
├── Backend/               # Spring Boot REST API (Port 8081)
│   ├── src/main/java/com/ASE/Infocur/site/
│   │   ├── api/           # REST Controllers (Bookings, Events, Sessions, PhotoProgress, Auth)
│   │   ├── configuration/ # Security, CORS, and AWS S3 configurations
│   │   ├── entity/        # MongoDB Document models
│   │   ├── repository/    # Spring Data MongoDB repositories
│   │   └── service/       # Business logic, Email OTP & AWS S3 file upload services
│   └── pom.xml
├── Frontend/              # Public & Client React Web Application
└── Admin/                 # Admin Management React Dashboard
```

---

## Getting Started

### Prerequisites
- **Java 17+** and **Maven**
- **Node.js** (v18+) and **npm**
- **MongoDB** instance (Local or MongoDB Atlas)
- **AWS S3** bucket and IAM credentials

### 1. Configure & Run the Backend
Create `Backend/src/main/resources/application-secret.properties` (automatically imported by `application.properties`):
```properties
spring.data.mongodb.uri=mongodb+srv://<username>:<password>@<cluster>/infocur-sitedb
cloud.aws.s3.endpoint=https://s3.ap-south-1.amazonaws.com
cloud.aws.credentials.access-key=YOUR_AWS_ACCESS_KEY
cloud.aws.credentials.secret-key=YOUR_AWS_SECRET_KEY
spring.mail.username=your_email@gmail.com
spring.mail.password=your_app_password
```
Build and run the Spring Boot application:
```bash
cd Backend
./mvnw clean install
./mvnw spring-boot:run
```
The REST API will start on `http://localhost:8081`.

### 2. Run the Client Portal
```bash
cd Frontend
npm install
npm run dev
```

### 3. Run the Admin Dashboard
```bash
cd Admin
npm install
npm run dev
```

### Cloning Backend ###

* git clone https://dismitha-admin@bitbucket.org/dismitha/ase-infocur.git
* go to backend folder
* open intellij idea IDE and open the project
* in terminal -> cd Backend
* mvn clean install


