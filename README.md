# Dealership Review Portal

## Project Overview

The Dealership Review Portal is a full-stack web application designed to allow customers to view, filter, and submit reviews for car dealerships across the United States. This portal aims to bring transparency to the dealership's customer experience by displaying customer feedback, thus building trust with new and existing customers. This project was developed as part of a capstone project in the **IBM Developer Skills Network** for the IBM Full-Stack Software Developer Profesional certificate course.

## Features

### General Features
- **Anonymous Users:**
  - View the "Contact Us" and "About Us" pages.
  - View a list of all dealerships.
  - Filter dealerships by state.
  - View dealership details and reviews.
  - Log in with credentials.

- **Authorized Users:**
  - Submit reviews for any dealership.
  - Provide details such as purchase status, purchase date, car make, model, and year in their review.
  - View their review at the top of the list after submission.

- **Admin Users:**
  - Log in to the admin site to manage dealership information.
  - Add new car make, model, and other attributes.

## Tech Stack

- **Frontend:** React, Django Templates, Bootstrap
- **Backend:** Django, Django REST Framework, Node.js, Express
- **Database:** MongoDB (for dealership and review data), SQLite (for car make/model data)
- **Deployment and DevOps:** Docker, Kubernetes, IBM Cloud Code Engine
- **Sentiment Analysis Service:** IBM Code Engine API for review sentiment analysis

## Project Structure

- **Dealership Website (Django App):** 
  - Provides user interfaces and manages user sessions.
  - Serves static and dynamic pages using Django views and templates.
  
- **Dealerships and Reviews Service (Node.js Express):** 
  - Manages data for dealerships and reviews stored in MongoDB.
  - Runs as a microservice in a Docker container.

- **Sentiment Analyzer Service:** 
  - Deployed on IBM Cloud Code Engine, analyzes review sentiment.

## API Endpoints

### Django Application Endpoints
| Endpoint                     | Description                    |
|------------------------------|--------------------------------|
| `/get_cars/`                 | Retrieves list of car makes/models |
| `/get_dealers/`              | Lists all dealerships          |
| `/get_dealers/:state`        | Lists dealerships by state     |
| `/dealer/:id`                | Retrieves details for a specific dealer |
| `/review/dealer/:id`         | Lists reviews for a dealer     |
| `/add_review/`               | Allows users to add a new review |

### Dealerships and Reviews Service (Express) Endpoints
| Endpoint                     | Description                    |
|------------------------------|--------------------------------|
| `/fetchDealers`              | Fetches list of dealerships    |
| `/fetchDealer/:id`           | Fetches details for a dealership by ID |
| `/fetchReviews`              | Fetches all reviews            |
| `/fetchReview/dealer/:id`    | Fetches reviews for a dealer by ID |
| `/insertReview`              | Adds a new review              |

### Sentiment Analysis Service
| Endpoint                       | Description                    |
|--------------------------------|--------------------------------|
| `/analyze/:text`               | Analyzes the sentiment of a text (positive, negative, or neutral) |


