# 🚗 Car Rental Management System

A comprehensive web-based car rental management system built with PHP, MySQL, and modern web technologies. This project provides a complete solution for car rental businesses with both user and admin interfaces.

## 📋 Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [System Requirements](#system-requirements)
- [Installation Guide](#installation-guide)
- [Database Schema](#database-schema)
- [User Features](#user-features)
- [Admin Features](#admin-features)
- [File Structure](#file-structure)
- [API Endpoints](#api-endpoints)
- [Security Features](#security-features)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### 🎯 Core Functionality
- **User Registration & Authentication**: Secure login system with session management
- **Car Catalog**: Browse available cars with detailed information
- **Booking System**: Complete car reservation workflow
- **Payment Processing**: Integrated payment gateway with credit card validation
- **Admin Dashboard**: Comprehensive management interface
- **Feedback System**: User feedback collection and management
- **Responsive Design**: Mobile-friendly interface

### 🔐 Security Features
- Password encryption using MD5
- Session-based authentication
- SQL injection prevention
- Input validation and sanitization
- Back navigation prevention

## 🛠 Technology Stack

- **Backend**: PHP 8.0+
- **Database**: MySQL 10.4+
- **Frontend**: HTML5, CSS3, JavaScript
- **Server**: XAMPP/Apache
- **Payment**: Credit card processing with Cleave.js
- **Styling**: Custom CSS with Bootstrap components
- **Icons**: Font Awesome

## 💻 System Requirements

- **Web Server**: XAMPP, WAMP, or similar local server
- **PHP**: Version 8.0 or higher
- **MySQL**: Version 10.4 or higher
- **Browser**: Modern web browser with JavaScript enabled
- **RAM**: Minimum 2GB (4GB recommended)
- **Storage**: 100MB free space

## 🚀 Installation Guide

### Step 1: Environment Setup
1. Download and install [XAMPP](https://www.apachefriends.org/download.html)
2. Start Apache and MySQL services from XAMPP Control Panel

### Step 2: Project Setup
1. Clone or download this repository
2. Extract files to `htdocs` folder in XAMPP directory
3. Navigate to project folder in your file manager

### Step 3: Database Configuration
1. Open phpMyAdmin (http://localhost/phpmyadmin)
2. Create a new database named `carproject`
3. Import the SQL file from `database/carproject.sql`
4. Verify database connection in `connection.php`

### Step 4: Access the Application
1. Open your web browser
2. Navigate to `http://localhost/[project-folder-name]`
3. The application should now be running!

## 🗄 Database Schema

### Tables Overview

| Table | Purpose | Key Fields |
|-------|---------|------------|
| `users` | User accounts | EMAIL, PASSWORD, NAME, PHONE |
| `admin` | Admin authentication | ADMIN_ID, ADMIN_PASSWORD |
| `cars` | Vehicle inventory | CAR_ID, CAR_NAME, FUEL_TYPE, PRICE, AVAILABLE |
| `booking` | Reservation records | BOOK_ID, CAR_ID, EMAIL, BOOK_DATE, RETURN_DATE |
| `payment` | Transaction records | PAYMENT_ID, BOOK_ID, AMOUNT, PAYMENT_DATE |
| `feedback` | User feedback | FEEDBACK_ID, EMAIL, COMMENT |

### Sample Data
The database comes pre-loaded with:
- Sample cars (Ferrari, Lamborghini, Porsche, Swift)
- Default admin credentials (ADMIN/ADMIN)
- Sample booking records

## 👤 User Features

### Authentication
- **Registration**: New user account creation
- **Login**: Secure authentication with email/password
- **Session Management**: Automatic logout and security

### Car Browsing
- **Catalog View**: Browse all available vehicles
- **Search Functionality**: Filter cars by various criteria
- **Detailed Information**: View car specifications, pricing, and images

### Booking Process
1. **Car Selection**: Choose from available vehicles
2. **Booking Form**: Enter pickup/drop-off details
3. **Date Selection**: Choose rental duration
4. **Payment Processing**: Secure credit card payment
5. **Confirmation**: Booking confirmation and receipt

### Additional Features
- **Booking History**: View past and current reservations
- **Feedback System**: Submit reviews and comments
- **Profile Management**: Update personal information

## 🔧 Admin Features

### Dashboard Overview
- **Statistics**: View booking counts, revenue, user statistics
- **Quick Actions**: Access to all management functions
- **Real-time Updates**: Live data refresh

### Vehicle Management
- **Add Cars**: Upload new vehicles with images
- **Edit Cars**: Modify vehicle information
- **Delete Cars**: Remove vehicles from inventory
- **Availability Control**: Mark cars as available/unavailable

### Booking Management
- **View All Bookings**: Complete booking overview
- **Approve/Reject**: Manage booking requests
- **Process Returns**: Handle vehicle returns
- **Booking History**: Track all transactions

### User Management
- **User List**: View all registered users
- **User Details**: Access user information
- **Account Management**: Manage user accounts

### System Administration
- **Feedback Review**: View and manage user feedback
- **Payment Tracking**: Monitor payment transactions
- **System Reports**: Generate business reports

## 📁 File Structure

```
Fenil-Car Rental/
├── 📄 index.php                 # Main landing page and login
├── 📄 register.php              # User registration
├── 📄 cardetails.php            # Car catalog and details
├── 📄 booking.php               # Booking form and process
├── 📄 payment.php               # Payment processing
├── 📄 connection.php            # Database connection
├── 📄 main.js                   # Payment validation scripts
├── 📁 admin/                    # Admin interface files
│   ├── 📄 admindash.php         # Admin dashboard
│   ├── 📄 adminlogin.php        # Admin authentication
│   ├── 📄 addcar.php            # Add new vehicles
│   ├── 📄 adminbook.php         # Booking management
│   └── 📄 adminusers.php        # User management
├── 📁 css/                      # Stylesheets
│   ├── 📄 style.css             # Main styling
│   ├── 📄 form.css              # Form styling
│   ├── 📄 pay.css               # Payment page styling
│   └── 📄 adlog.css             # Admin login styling
├── 📁 images/                   # Vehicle and UI images
├── 📁 database/                 # Database files
│   └── 📄 carproject.sql        # Database schema and data
├── 📁 feedback/                 # Feedback system
│   └── 📄 Feedbacks.php         # Feedback processing
└── 📁 report/                   # Project documentation
    └── 📄 CarProjectFinalReport.pdf
```

## 🔌 API Endpoints

### User Endpoints
- `POST /index.php` - User login
- `POST /register.php` - User registration
- `GET /cardetails.php` - Car catalog
- `POST /booking.php` - Create booking
- `POST /payment.php` - Process payment
- `POST /feedback/Feedbacks.php` - Submit feedback

### Admin Endpoints
- `POST /adminlogin.php` - Admin authentication
- `GET /admindash.php` - Admin dashboard
- `POST /addcar.php` - Add new car
- `POST /adminbook.php` - Manage bookings
- `POST /adminusers.php` - User management

## 🔒 Security Features

### Authentication & Authorization
- **Session Management**: Secure session handling
- **Password Encryption**: MD5 hashing for passwords
- **Access Control**: Role-based access (User/Admin)
- **SQL Injection Prevention**: Prepared statements and input sanitization

### Data Protection
- **Input Validation**: Client and server-side validation
- **XSS Prevention**: Output encoding and sanitization
- **CSRF Protection**: Form token validation
- **Secure Headers**: HTTP security headers

### Payment Security
- **Credit Card Validation**: Real-time card number validation
- **Payment Processing**: Secure transaction handling
- **Data Encryption**: Sensitive data protection

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Development Guidelines
- Follow PHP coding standards
- Add comments for complex logic
- Test thoroughly before submitting
- Update documentation as needed

## 🌟 Support

If you find this project helpful, please give it a ⭐️ star!

### Contact
For questions or support, please open an issue on GitHub or contact the development team.

---
