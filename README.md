# AirBnB Clone Project

## Overview
The **AirBnB Clone Project** is a full-stack web application that replicates the core features of the AirBnB platform.  
The goal is to build a functional clone that allows users to register, log in, list properties, book stays, and manage their bookings.

This project aims to strengthen skills in **web development**, **API design**, **database management**, and **frontend-backend integration**.

---

##  Project Goals
- Build a scalable web application using modern web technologies.
- Implement user authentication and session management.
- Design RESTful APIs for listing and booking properties.
- Create an intuitive and responsive user interface.
- Practice version control and team collaboration using Git and GitHub.

---

## Tech Stack
**Backend:**
- Python / Flask or Django  
- RESTful API design  
- SQLite or MySQL for database management  

**Frontend:**
- HTML, CSS, JavaScript  
- React.js or basic Bootstrap-based UI  

**Version Control & Deployment:**
- Git & GitHub  
- Render / Heroku / AWS (for hosting)

---

## Author
**Davis Mwenda**  
- GitHub: [@ShuaibDoe](https://github.com/ShuaibDoe)  
- Email: ddoedavies@gmail.com

---

## Getting Started
Clone the repository:
```bash
git clone https://github.com/ShuaibDoe/airbnb-clone-project.git

---

# Team Roles

- In the AirBnB Clone Project, successful collaboration relies on each team member fulfilling a specific role.

## 1. Project Manager (PM)
##Responsibilities:

- Oversees project planning, scheduling, and progress tracking.
- Ensures effective communication across all teams.
- Manages deadlines, resources, and deliverables to meet project goals.
- Acts as a bridge between stakeholders and the development team.

## 2. Backend Developer

##Responsibilities:

- Designs, develops, and maintains the server-side logic of the application.
- Builds APIs to handle user requests, property listings, and bookings.
- Implements authentication, authorization, and data validation.
- Ensures scalability, performance, and security of backend systems.

## 3. Database Administrator (DBA)

##Responsibilities:
- Designs and manages the project database schema.
- Ensures data integrity, security, and backup management.
- Optimizes database queries for performance and reliability.
- Collaborates with backend developers to integrate data models efficiently.

## 4. Frontend Developer

##Responsibilities:
- Builds the user interface (UI) and ensures an excellent user experience (UX).
- Implements responsive designs using HTML, CSS, JavaScript (and possibly React).
- Integrates frontend components with backend APIs.
- Tests and debugs UI features for smooth functionality across devices.

## 5. Quality Assurance (QA) Engineer

##Responsibilities:
- Develops and executes test plans to ensure system reliability.
- Conducts functional, integration, and regression testing.
- Identifies bugs and collaborates with developers to resolve them.
- Ensures that the final product meets performance and usability standards.

## 6. DevOps Engineer

##Responsibilities:
- Automates deployment, monitoring, and scaling processes.
- Manages cloud infrastructure (e.g., AWS, Render, or Heroku).
- Sets up Continuous Integration/Continuous Deployment (CI/CD) pipelines.
- Ensures application uptime, security, and version control best practices.

## 7. UI/UX Designer

##Responsibilities:
- Conducts user research and creates wireframes and prototypes.
- Defines the look and feel of the product in line with usability principles.
- Works closely with frontend developers to implement design systems.
- Ensures that the app is intuitive and visually appealing.

---

## Technology Stack

- The AirBnB Clone Project leverages a modern, full-stack technology ecosystem designed for scalability, performance, and maintainability.
- Each component of the stack plays a specific role in delivering a seamless end-to-end user experience.

## Backend Technologies

-Django: A powerful Python web framework used for building the core backend logic, RESTful APIs, and handling authentication, authorization, and data models.
-Django REST Framework (DRF): Simplifies API development by providing tools for serialization, authentication, and request handling.
-GraphQL (optional): Enables flexible data queries, allowing clients to request only the data they need — improving performance and efficiency.

## Database

-PostgreSQL: A robust and scalable relational database used to store structured data such as users, properties, bookings, and reviews.
-SQLite (for development): A lightweight database used for local testing before deploying to production with PostgreSQL.

## Frontend Technologies

-HTML5 & CSS3: Used for building and styling the user interface, ensuring responsive and accessible layouts.
-JavaScript (ES6+): Adds interactivity and dynamic functionality to the web pages.
-React.js: A JavaScript library used for creating reusable UI components and managing client-side rendering efficiently.
-Bootstrap / Tailwind CSS: Speeds up UI development with pre-styled responsive components.

## Development & Version Control

-Git: Used for version control to track changes and collaborate effectively across team members.
-GitHub: Serves as the remote repository for code hosting, collaboration, and project management.

## Deployment & DevOps

-Docker: Containerizes the application to ensure consistency across development and production environments.
-Render / Heroku / AWS: Cloud platforms for deploying and hosting the application securely and reliably.
-CI/CD Pipelines: Automates testing and deployment to maintain continuous integration and delivery.

## Testing & Quality Assurance

-Pytest / Unittest: Frameworks for automated testing of backend logic and API endpoints.
-Postman: Used to test and debug RESTful APIs during development.
-Selenium / Cypress: Tools for end-to-end testing of frontend user flows.

---

## Database Design

- The database for the AirBnB Clone Project is structured to manage users, properties, bookings, reviews, and payments efficiently.
- It follows a relational model, ensuring data integrity and enabling clear relationships between entities.

## 1. Users

- Represents all individuals who interact with the platform — both guests and hosts.

#Key Fields:

-id – Primary Key, unique identifier for each user
-name – Full name of the user
-email – Unique email address (used for authentication)
-password_hash – Encrypted user password
-role – Defines whether the user is a host or guest

#Relationships:

- A user (host) can list multiple properties.
- A user (guest) can make multiple bookings and write reviews.

## 2. Properties

- Represents accommodations listed by hosts.

#Key Fields:

-id – Primary Key
-host_id – Foreign Key → Users(id) (property owner)
-title – Property name or headline
-description – Detailed description of the property
-price_per_night – Cost per night for booking

#Relationships:

- A property belongs to one host (user).
- A property can have many bookings and reviews.

## 3. Bookings

- Represents reservations made by guests for specific properties.

#Key Fields:

-id – Primary Key
-user_id – Foreign Key → Users(id) (guest who booked)
-property_id – Foreign Key → Properties(id)
-check_in_date – Start date of the stay
-check_out_date – End date of the stay

#Relationships:

- A booking belongs to one user and one property.
- A booking may have one payment record.

## 4. Reviews

- Stores feedback provided by guests about their stays.

#Key Fields:

-id – Primary Key
-user_id – Foreign Key → Users(id)
-property_id – Foreign Key → Properties(id)
-rating – Numeric score (e.g., 1–5)
-comment – Text feedback from the guest

#Relationships:

- A user can post multiple reviews.
- Each review belongs to one property.

## 5. Payments

- Tracks financial transactions related to bookings.

#Key Fields:

-id – Primary Key
-booking_id – Foreign Key → Bookings(id)
-amount – Total amount paid
-payment_status – Status (e.g., pending, completed, failed)
-payment_date – Date of transaction

#Relationships:

- Each payment is linked to one booking.
- A booking can have one or more payment attempts.

## Entity Relationships Summary
#Relationship Type	Description#
1 One-to-Many	A user can have multiple properties.
2 One-to-Many	A property can have multiple bookings and reviews.
3 One-to-One	A booking can have one payment.
4 Many-to-One	Each booking belongs to one user and one property.