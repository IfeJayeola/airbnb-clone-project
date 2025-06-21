# airbnb-clone-project

## Team Roles

**Business analyst:** studies the customer work flow and get feedback from stackholder. The business analyst turns needs into requirements for the team. 

**Product owner:** ensures that the final product satisfies customers by designing strategies and defining the project vision. 

*Product owner is more customer oriented while business analyst of more technical*

**Project manager:** manages and motivates the team and ensures that the project meet the deadline and does not exceed the budget. 

**UI/UX designer:** creates design and draws the user journey map for user's experience. 

**Software architect:** makes decisions on the tools and platforms to use. He also designs software architecture and sets code standard and does code review. 

**Software developer:** does the actual coding and engineering is the product. 

**Quality assurance:** makes sure that the software product meets the functional and non functional requirements.

**Test automation engineer:** designs and maintains test script. 

**DevOps engineer:** builds CI/CD Pipeline. 

## Technology Stack

- **Django**: Python web framework used for building the RESTful API.
- **Django REST Framework:** P creating and managing RESTful APIs.
- **PostgreSQL:** relational database for data storage.
- **GraphQL:** querying language.
- **Celery:** For handling asynchronous tasks such as sending notifications or processing payments.
Redis: Used for caching and session management.
- **Docker:** Containerization tool for consistent development and deployment environments.
- **CI/CD Pipelines:** Automated pipelines for testing and deploying code changes. 

## Database Design

### Entities and Relationships

#### 1. Users
- `id`: Unique identifier for the user
- `name`: Full name of the user
- `email`: Email address (must be unique)
- `password`: Hashed password for login
- `role`: Role of the user (`host` or `guest`)

**Relationships:**
- A user can own multiple properties (if host)
- A user can make multiple bookings (if guest)
- A user can leave multiple reviews

---

#### 2. Properties
- `id`: Unique identifier for the property
- `title`: Name or title of the property listing
- `description`: Details about the property
- `location`: Address or general location
- `price_per_night`: Rental cost per night
- `owner_id`: The `id` of the user who owns this property

**Relationships:**
- A property belongs to one user (host)
- A property can have multiple bookings
- A property can have multiple reviews

---

#### 3. Bookings
- `id`: Unique identifier for the booking
- `user_id`: ID of the guest who made the booking
- `property_id`: ID of the booked property
- `start_date`: Date the booking begins
- `end_date`: Date the booking ends
- `status`: Booking status (`confirmed`, `cancelled`, etc.)

**Relationships:**
- A booking belongs to one user and one property
- A booking can have one payment
- A booking can receive one review

---

#### 4. Reviews
- `id`: Unique identifier for the review
- `user_id`: ID of the reviewer (guest)
- `property_id`: ID of the reviewed property
- `rating`: Star rating (e.g. 1-5)
- `comment`: Written feedback from the guest

**Relationships:**
- A review belongs to one user and one property
- A booking can have one review

---

#### 5. Payments
- `id`: Unique identifier for the payment
- `booking_id`: ID of the related booking
- `amount`: Total amount paid
- `payment_date`: When the payment was made
- `status`: Payment status (`paid`, `pending`, `failed`)

**Relationships:**
- A payment belongs to one booking

## Feature Breakdown
- `API Documentation:` explains how an api is used. It makes development faster and coll easier. 
- `User Authentication:` means verifying who a user is. It helps with security and to give user personalized content. 
- `Property Management:`manages property listing. Through this, property listings are created, read, updated and deleted. 
- `Booking System:` manages details of bookings. It's creates, retrieve and update bookings. It helps to track each booking. 
- `Payment Processing:` handles the electronic payment mass for booking. It helps to make bookings with convenience. 
- `Review System:` handle reviews on property. It helps users to do on comment about their experience with a property. 
- `Database Optimizations:` uses indexing for fast data retrieve and caching to reduce database load. This improves user's experience 
## API Security

## CI/CD Pipeline
