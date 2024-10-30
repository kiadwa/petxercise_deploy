# Lab-01-Group-06

# PetXercise

## Project Overview
PetXercise is a one-stop service platform for pet owners, pet trainers, and professionals in the pet industry. The platform uses AI-assisted features to provide personalized pet care recommendations, supports appointment and service management, simplifying the related processes of pet care and training to provide users with a better experience and higher service quality.

### Project Objectives
- Provide pet owners with a safe, efficient platform to easily find and book services like pet training, grooming, and veterinary care.
- Help service providers better manage bookings and communicate with customers.
- Offer personalized pet care advice based on AI.

### Key Features
- User authentication system (distinguishing between admin and regular users).
- Database system for managing users, pets, trainers, service providers, and orders.
- AI-based personalized pet care suggestions.
- Intuitive user interface supporting appointment systems and trainer lists.
- Provides RESTful API for managing user data and services.

---

## Installation Instructions

### Prerequisites
Ensure you have the following installed when setting up the project locally:
- **Python 3.12**
- **Django** (as specified in `requirements.txt`)
- **MySQL** database
- **mysqlclient** (for Python and MySQL connection)
- **Postman** (for API testing)
- **PyCharm** (recommended development IDE)

Frontend dependencies:
- **vite**
- **bootstrap**
- **axios**

### Installation Steps

1. **Clone the project code**:
   ```bash
   git clone https://github.sydney.edu.au/2024-INTERNET-SOFTWARE-PLATFORM/Lab-01-Group-06.git
   ```

2. **Set up a virtual environment**:
   ```bash
   python -m venv env
   source env/bin/activate  # For Windows: .\env\Scriptsctivate
   ```

3. **Install Python dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Install frontend dependencies**:
   ```bash
   npm install
   ```
5. **Install the OpenAI client library**:
   ```bash
   pip install openai
   ```

**Set up the OpenAI API key**:
   - Go to the [OpenAI API keys](https://platform.openai.com/account/api-keys) page to generate your API key.
   - Configure your API key in the environment variables, for example:
     ```bash
     export OPENAI_API_KEY='your-api-key'
     ```

6. **Configure MySQL database**:
   - Ensure MySQL is installed and running.
   - Create a project database:
     ```sql
     CREATE DATABASE petxercise_db;
     ```
   - Update the database configuration in `settings.py`:
     ```python
      DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'ELEC9609',
           'USER': 'ELEC9609',
           'PASSWORD': 'ELEC9609',
           'HOST': 'localhost',
           'PORT': '3306',
      }
     ```

7. **Migrate the database**:
   
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

8. **Create a superuser** (for accessing Django admin):
   ```bash
   python manage.py createsuperuser
   ```

---

## Configuration and Environment Setup

### Frontend Configuration
Ensure the `vite.config.js` file is correctly set up and that Bootstrap and axios are installed.

---

## Usage Instructions

1. **Start the Django development server**:
   ```bash
   python manage.py runserver
   ```

   The application will run at `http://127.0.0.1:8000/`.

2. **Start the frontend**:
   Run vite for frontend development:
   ```bash
   npm run dev
   ```
   The frontend can be accessed via the specified port (e.g., `http://localhost:5173`).

---

## API Documentation

This project implements the following RESTful API endpoints for managing users, pets, trainers, service orders, and payments.

The basic descriptions of the APIs are provided here. For actual calls, refer to Backend/README.md.

### 1. **User Endpoints**

- **GET /rest/user**: Retrieve user information based on various query parameters (e.g., uid, dob, admin, verification).
- **POST /rest/user**: Register a new user.
- **PUT /rest/user**: Update existing user information.
- **DELETE /rest/user**: Delete a user.

### 2. **User Avatar Endpoints**

- **GET /rest/user_avatar**: Retrieve user avatar information based on uid and avatar.
- **POST /rest/user_avatar**: Create a new avatar for the user.
- **PUT /rest/user_avatar**: Update the existing avatar.
- **DELETE /rest/user_avatar**: Delete a user avatar.

### 3. **Pet Endpoints**

- **GET /rest/pet**: Retrieve pet information based on various query parameters (e.g., pid, uid, age, dob).
- **POST /rest/pet**: Register a new pet.
- **PUT /rest/pet**: Update existing pet information.
- **DELETE /rest/pet**: Delete a pet.

### 4. **Pet Avatar Endpoints**

- **GET /rest/pet_avatar**: Retrieve pet avatar information based on pid and avatar.
- **POST /rest/pet_avatar**: Create a new pet avatar.
- **PUT /rest/pet_avatar**: Update the existing pet avatar.
- **DELETE /rest/pet_avatar**: Delete a pet avatar.

### 5. **Provider Endpoints**

- **GET /rest/provider**: Retrieve provider information based on various query parameters (e.g., provid, verification).
- **POST /rest/provider**: Register a new provider.
- **PUT /rest/provider**: Update existing provider information.
- **DELETE /rest/provider**: Delete a provider.

### 6. **Trainer Endpoints**

- **GET /rest/trainer**: Retrieve trainer information based on various query parameters (e.g., tid, provid, dob, verification).
- **POST /rest/trainer**: Register a new trainer.
- **PUT /rest/trainer**: Update existing trainer information.
- **DELETE /rest/trainer**: Delete a trainer.

### 7. **Trainer Avatar Endpoints**

- **GET /rest/trainer_avatar**: Retrieve trainer avatar information based on tid and avatar.
- **POST /rest/trainer_avatar**: Create a new trainer avatar.
- **PUT /rest/trainer_avatar**: Update the existing trainer avatar.
- **DELETE /rest/trainer_avatar**: Delete a trainer avatar.

### 8. **Service Order Endpoints**

- **GET /rest/service_order**: Retrieve service order information based on various query parameters (e.g., order_id, pid, uid, tid, order_date).
- **POST /rest/service_order**: Create a new service order.
- **PUT /rest/service_order**: Update existing service orders.
- **DELETE /rest/service_order**: Delete a service order.

### 9. **Payment Endpoints**

- **GET /rest/payment**: Retrieve payment information based on various query parameters (e.g., paymentid, order_id).
- **POST /rest/payment**: Create new payment information.
- **PUT /rest/payment**: Update existing payment information.
- **DELETE /rest/payment**: Delete payment information.

---#   p e t x e r c i s e _ d e p l o y  
 