MAM Tours  Car Rental Made Simple

MAM Tours is a modern car rental platform designed to simplify vehicle booking and rental management. It provides a seamless experience for customers booking cars and administrators managing operations.

The system is built to be secure, scalable, and practical for real-world rental businesses.

Overview

MAM Tours is more than a booking system. It is a complete rental management solution built with efficiency and usability in mind.

Secure Registration and Verification

Customers can register, upload identification documents, and undergo verification before accessing full platform features. This ensures compliance and reduces risk.

Smart Booking System

Real-time vehicle availability

Automatic price calculation

Streamlined booking workflow

Flexible Payment Options

The platform supports:

Stripe (card payments)

MTN Mobile Money

Airtel Money

Bank transfers

Cash payments

Administrative Dashboard

Administrators can manage:

Vehicles

Bookings

Customers

Identity verifications

Reviews

Payments

Automated Notifications

The system sends:

Booking confirmations

Payment confirmations

Pickup reminders

Email and SMS notifications

Customer Reviews

Customers can leave feedback to help maintain service quality and transparency.

Automated Invoice Generation

Professional PDF invoices are generated automatically for completed bookings.

System Requirements

Before running the application locally, ensure you have:

PHP 7.3 or higher

MySQL 5.7 or higher

Composer

Node.js and NPM

Running Locally
Step 1: Install Dependencies
composer install
npm install
npm run build

Step 2: Configure Environment
cp .env.example .env
php artisan key:generate


Update the .env file with your database credentials:

DB_DATABASE=mam_tours
DB_USERNAME=root
DB_PASSWORD=your_password

Step 3: Set Up the Database
php artisan migrate
php artisan db:seed

Step 4: Start the Development Server
php artisan serve


Access the application at:

http://127.0.0.1:8000

Production Deployment (Railway)
1. Push Code to GitHub
git add .
git commit -m "Production ready"
git push origin main

2. Deploy on Railway

Sign in to railway.app

Create a new project

Deploy from GitHub repository

Add a MySQL database

3. Configure Environment Variables

Add the following variables in Railway:

APP_ENV=production
APP_DEBUG=false
APP_URL=${{RAILWAY_PUBLIC_DOMAIN}}

DB_HOST=${{MYSQL_HOST}}
DB_DATABASE=${{MYSQL_DATABASE}}
DB_USERNAME=${{MYSQL_USER}}
DB_PASSWORD=${{MYSQL_PASSWORD}}

STRIPE_KEY=your_key
STRIPE_SECRET=your_secret

4. Generate a Public Domain

Navigate to:
Settings → Networking → Generate Domain

Your application will then be publicly accessible.

Payment Configuration

To activate payment functionality:

Stripe

Obtain API keys from stripe.com and add them to the .env file.

Mobile Money

Register for MTN and Airtel Money credentials and configure them within the environment file.

Email and SMS Configuration

Supported services include:

Mailgun

SendGrid

SMTP providers

Twilio

Africa’s Talking

Add your provider credentials to the .env file to enable notifications.

Scheduled Tasks

To enable automated reminders and background tasks, add the following to your server’s crontab:

* * * * * cd /your-project-path && php artisan schedule:run >> /dev/null 2>&1

Project Structure
app/
├── Console/
├── Http/Controllers/
├── Models/
└── Services/

database/
├── migrations/
└── seeders/

resources/
├── css/
├── js/
└── views/

public/
routes/web.php
tests/


The structure follows Laravel best practices for scalability and maintainability.

Default Administrator Account

After running the database seeder:

Email: wilberofficial2001@gmail.com

Password: password

This password must be changed immediately in production.

Security Features

The application includes:

CSRF protection

XSS and SQL injection prevention

Secure bcrypt password hashing

Rate limiting

Administrative activity logging

Optional two-factor authentication support

Unverified users are restricted to cash payments until identification is approved.

Testing

Run automated tests using:

php artisan test
php artisan test --testsuite=Feature
php artisan test --coverage

Technology Stack

Laravel 8

Vue.js 3

Tailwind CSS

Stripe API

MySQL

MAM Tours is designed to provide a reliable, secure, and scalable car rental solution for modern businesses.
