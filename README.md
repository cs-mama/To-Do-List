To-Do List Web Application
Overview
This project is a simple To-Do List web application built with Flask, GraphQL, and Keycloak for authentication. The app allows users to manage their tasks and offers an option to purchase a Pro license, enabling users to upload images to their tasks. The entire application is secured using Keycloak, and payments are processed via Stripe.

Features
User Authentication: Secure login using Keycloak.
GraphQL API: CRUD operations for To-Do items.
Pro License: Option to purchase a Pro license via Stripe to enable image uploads.
Simple UI: Basic frontend interface to interact with the application.
Dockerized Setup: Deployable via Docker.
Prerequisites
Python 3.8+
Flask
Keycloak (Docker setup recommended)
Stripe account (for testing payments)
Setup Instructions

1. Clone the Repository

git clone
cd your-repo-name (https://github.com/cs-mama/To-Do-List) 2. Install Dependencies
Create a virtual environment and install the required packages:

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt 3. Configure Environment Variables
Create a .env file in the root directory and add the following:

KEYCLOAK_URL=http://localhost:8080/auth
REALM_NAME= Chandra Sekhar
CLIENT_ID=https://www.keycloak.org/
STRIPE_SECRET_KEY=https://www.keycloak.org/getting-started/getting-started-docker
STRIPE_PUBLISHABLE_KEY=[stripe-publishable-key](https://www.keycloak.org/getting-started/getting-started-docker) 4. Set Up Keycloak
Follow the Keycloak Docker setup guide to set up Keycloak locally.
Create a new realm and client in Keycloak.
Update the .env file with your Keycloak realm and client details. 5. Run the Application
Ensure your Keycloak server is running, then start the Flask application:

flask run 6. Access the Application
Open your browser and navigate to http://localhost:5000 to access the application.

7. Testing Payments
   To test the Stripe payment integration, use the test card numbers provided by Stripe. The purchase process should simulate a successful payment.

8. Running with Docker (Optional)
   If you want to deploy the application using Docker:

Build the Docker image:

docker build -t todo-app .
Run the container:

docker run -p 5000:5000 todo-app
