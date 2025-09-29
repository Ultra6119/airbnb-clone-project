# Airbnb Clone Project

## Overview

The Airbnb Clone Project is a comprehensive full-stack web application that replicates the core functionality of Airbnb. This project focuses on building a scalable backend system, robust database architecture, secure APIs, and modern CI/CD deployment pipelines.

## Project Goals

- Simulate real-world software development workflows
- Understand scalable backend systems and relational databases
- Practice implementing API security and CI/CD pipelines
- Collaborate using Git, GitHub, and team-based practices

## API Security

To protect user data and ensure secure interactions within the Airbnb Clone platform, the following API security measures will be implemented:

- **Authentication**
  - Token-based authentication (e.g., JWT) to secure endpoints
  - Login required for accessing user-specific data or actions

- **Authorization**
  - Role-based access control to limit access to certain resources (e.g., admin vs. regular user)
  - Only listing owners can modify or delete their listings

- **Input Validation & Sanitization**
  - All incoming data is validated and sanitized to prevent SQL injection and XSS attacks
  - Strict schema validation using Django serializers and GraphQL schemas

- **Rate Limiting**
  - Protects the API from brute-force and DoS attacks by limiting request rates per IP

- **HTTPS Enforcement**
  - Ensures all communication between client and server is encrypted in production

- **Error Handling & Logging**
  - Secure error messages (no sensitive data exposed)
  - Logging of failed login attempts and suspicious activities

These measures help create a secure and resilient API that protects user information and maintains the integrity of the system.

## Feature Breakdown

This project includes the following key features that replicate core functionality of the Airbnb platform:

- **User Registration and Authentication**
  - Secure signup, login, and logout functionality
  - Password hashing and user session management

- **Listing Management**
  - Hosts can create, update, and delete property listings
  - Listings include title, description, photos, location, and price

- **Search and Filtering**
  - Users can search listings by location, date, and price range
  - Filter options for amenities, availability, and ratings

- **Booking System**
  - Users can book available listings for specific dates
  - Conflict-free date management and validation

- **Review and Ratings**
  - Guests can leave reviews and rate their stay
  - Hosts can view feedback for their listings

- **Admin Panel**
  - Admin users can manage users, listings, and bookings
  - Backend moderation tools for platform management

- **API Integration (GraphQL)**
  - Data is served via a GraphQL API
  - Efficient querying for frontend consu

## Technology Stack

- **Backend Framework**: Django
- **Database**: MySQL
- **API Layer**: GraphQL
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Version Control**: Git & GitHub

## Database Design

The Airbnb Clone database is designed to reflect real-world booking functionality. It uses a **relational schema** implemented in **MySQL** with the following core entities:

### 📊 Tables

- **User**
  - id (PK)
  - name
  - email
  - password_hash
  - date_joined

- **Listing**
  - id (PK)
  - host_id (FK → User.id)
  - title
  - description
  - location
  - price_per_night

- **Booking**
  - id (PK)
  - guest_id (FK → User.id)
  - listing_id (FK → Listing.id)
  - check_in
  - check_out
  - status

- **Review**
  - id (PK)
  - booking_id (FK → Booking.id)
  - rating
  - comment
  - created_at

### 🔗 Relationships

- A **User** can be both a host and a guest.
- A **Listing** is created by one User (host).
- A **Booking** is made by one User (guest) for one Listing.
- A **Review** is left after a Booking is completed.

This structure ensures data integrity and supports efficient querying for common operations like searching listings, managing bookings, and leaving reviews.


## Team Roles

| Role | Responsibilities |
|------|------------------|
| **Backend Developer** | Responsible for building and maintaining the server-side logic using Django. Works on API endpoints, authentication systems, and business logic implementation. |
| **Database Administrator (DBA)** | Designs and manages the MySQL database schema. Ensures data integrity, creates ERDs, optimizes queries, and handles data migrations. |
| **DevOps Engineer** | Implements Docker for containerization, sets up GitHub Actions for CI/CD, automates testing and deployment workflows, and ensures smooth operation of the development pipeline. |
| **Security Specialist** | Focuses on implementing security best practices, including API authentication, authorization, data encryption, and vulnerability mitigation. |
| **Project Manager** | Coordinates the team, manages timelines, distributes tasks, and ensures that the project adheres to scope and deadlines. Handles communication and progress tracking. |

