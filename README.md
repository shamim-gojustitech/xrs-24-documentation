
# Backend API Documentation

Welcome to the documentation for the [Your Project Name] backend API. This API serves as the backbone for managing various aspects of your application. Developed by [Your Name/Your Team], this API is built using Node.js, MongoDB, Express, and Mongoose.

## Introduction

The [Your Project Name] backend API provides a comprehensive set of endpoints to handle different sections of your application. Whether it's managing user data, handling orders, tracking sales, or maintaining inventory, this API is designed to meet your application's needs.

## Technologies Used

- **Node.js:** A robust JavaScript runtime for server-side development.
- **MongoDB:** A NoSQL database for efficient data storage and retrieval.
- **Express:** A minimalist web application framework for Node.js.
- **Mongoose:** An elegant MongoDB object modeling tool for Node.js.

## Project Structure

```
# 📦 xrs-new-backend
├─ ⚙️ config
│  ├─ 📜 messages.js
│  ├─ 🔐 passport.js
│  ├─ ☁️ spacesClient.js
│  ├─ ⚙️ systemConfig.js
│  └─ 📜 winston.js
├─ 🧾 controllers
│  ├─ 📜 attendance.js
│  ├─ 📜 combinedReports.js
│  ├─ 📜 expense.js
│  ├─ 📜 inventory.js
│  ├─ 📜 order.js
│  ├─ 📜 overtime.js
│  ├─ 📜 payroll.js
│  ├─ 📜 production.js
│  ├─ 📜 profile.js
│  ├─ 📜 sales.js
│  └─ 📜 supplier.js
├─ 🛠️ middleware
│  ├─ 📜 ensureRole.js
│  ├─ 📜 expressLogger.js
│  └─ 📜 spacesUploader.js
├─ 📊 models
│  ├─ 📜 attendance.js
│  ├─ 📜 expense.js
│  ├─ 📜 inventory.js
│  ├─ 📜 order.js
│  ├─ 📜 overtime.js
│  ├─ 📜 payroll.js
│  ├─ 📜 production.js
│  ├─ 📜 profile.js
│  ├─ 📜 sales.js
│  └─ 📜 supplier.js
├─ 🛣️ routes
│  ├─ 📂 admin
│  │  ├─ 📜 account.js
│  │  ├─ 📜 attendance.js
│  │  ├─ 📜 combinedReports.js
│  │  ├─ 📜 expense.js
│  │  ├─ 📜 index.js
│  │  ├─ 📜 inventory.js
│  │  ├─ 📜 order.js
│  │  ├─ 📜 overtime.js
│  │  ├─ 📜 payroll.js
│  │  ├─ 📜 production.js
│  │  ├─ 📜 profile.js
│  │  ├─ 📜 sales.js
│  │  └─ 📜 supplier.js
│  ├─ 📂 employee
│  │  ├─ 📜 index.js
│  │  └─ 📜 production.js
│  ├─ 📂 manager
│  │  ├─ 📜 account.js
│  │  ├─ 📜 attendance.js
│  │  ├─ 📜 expense.js
│  │  ├─ 📜 index.js
│  │  ├─ 📜 inventory.js
│  │  ├─ 📜 order.js
│  │  ├─ 📜 overtime.js
│  │  ├─ 📜 payroll.js
│  │  ├─ 📜 production.js
│  │  ├─ 📜 profile.js
│  │  ├─ 📜 sales.js
│  │  └─ 📜 supplier.js
│  ├─ 🔒 auth.js
│  └─ 📜 index.js
├─ 🔒 .env
├─ 📜 .eslintrc.json
├─ 📜 .gitignore
├─ 🔒 package-lock.json
├─ 📦 package.json
├─ 🚀 server.js
└─ 📜 README.md
```

## Usages

```
143.110.190.164:3004
```

## API Details
- [Backend API Documentation](#backend-api-documentation)
  - [Introduction](#introduction)
  - [Technologies Used](#technologies-used)
  - [Project Structure](#project-structure)
  - [Usages](#usages)
  - [API Details](#api-details)
- [Admin Level](#admin-level)
  - [User Section](#user-section)
    - [1. Create New User](#1-create-new-user)
    - [2. Get All Users](#2-get-all-users)
    - [3. Get User by ID](#3-get-user-by-id)
    - [4. Update User by ID](#4-update-user-by-id)
    - [5. Delete User by ID](#5-delete-user-by-id)
  - [Profile Section](#profile-section)
    - [1. Create New Profile](#1-create-new-profile)
    - [2. Get All Profiles](#2-get-all-profiles)
    - [3. Get Profile by ID](#3-get-profile-by-id)
    - [4. Update Profile by ID](#4-update-profile-by-id)
    - [5. Delete Profile by ID](#5-delete-profile-by-id)
  - [Attendance Section](#attendance-section)
    - [1. Create New Attendance Record](#1-create-new-attendance-record)
    - [2. Get All Attendance Records](#2-get-all-attendance-records)
    - [3. Update Attendance Record by ID](#3-update-attendance-record-by-id)
    - [4. Delete Attendance Record by ID](#4-delete-attendance-record-by-id)
    - [5. Attendance Absent Percentage Pie Chart](#5-attendance-absent-percentage-pie-chart)
    - [6. Get Date-wise Attendance Data](#6-get-date-wise-attendance-data)
  - [Order Section](#order-section)
    - [1. Create New Order](#1-create-new-order)
    - [2. Get All Orders](#2-get-all-orders)
    - [3. Get Order by ID](#3-get-order-by-id)
    - [4. Update Order by ID](#4-update-order-by-id)
    - [5. Delete Order by ID](#5-delete-order-by-id)
  - [Sales Section](#sales-section)
    - [1. Create New Sales Entry](#1-create-new-sales-entry)
    - [2. Get All Sales Entries](#2-get-all-sales-entries)
    - [3. Get Sales Entry by ID](#3-get-sales-entry-by-id)
    - [4. Update Sales Entry by ID](#4-update-sales-entry-by-id)
    - [5. Delete Sales Entry by ID](#5-delete-sales-entry-by-id)
    - [6. Get Sales Report](#6-get-sales-report)
    - [7. Get Date-wise Sales Data](#7-get-date-wise-sales-data)
  - [Inventory Section](#inventory-section)
    - [1. Create New Inventory](#1-create-new-inventory)
    - [2. Get All Inventory Items](#2-get-all-inventory-items)
    - [3. Get Inventory Item by ID](#3-get-inventory-item-by-id)
    - [4. Update Inventory Item by ID](#4-update-inventory-item-by-id)
    - [5. Delete Inventory Item by ID](#5-delete-inventory-item-by-id)
  - [Supplier Section](#supplier-section)
    - [1. Create New Supplier](#1-create-new-supplier)
    - [2. Get All Suppliers](#2-get-all-suppliers)
    - [3. Get Supplier by ID](#3-get-supplier-by-id)
    - [4. Update Supplier by ID](#4-update-supplier-by-id)
    - [5. Delete Supplier by ID](#5-delete-supplier-by-id)
  - [Production Section](#production-section)
    - [1. Create New Production](#1-create-new-production)
    - [2. Get All Productions](#2-get-all-productions)
    - [3. Get Production by ID](#3-get-production-by-id)
    - [4. Update Production by ID](#4-update-production-by-id)
    - [5. Delete Production by ID](#5-delete-production-by-id)
  - [Overtime Section](#overtime-section)
    - [1. Create New Overtime Entry](#1-create-new-overtime-entry)
    - [2. Get All Overtime Entries](#2-get-all-overtime-entries)
    - [3. Get Overtime Entry by ID](#3-get-overtime-entry-by-id)
    - [4. Update Overtime Entry by ID](#4-update-overtime-entry-by-id)
    - [5. Delete Overtime Entry by ID](#5-delete-overtime-entry-by-id)
  - [Payroll Section](#payroll-section)
    - [1. Create New Payroll Entry](#1-create-new-payroll-entry)
    - [2. Get All Payroll Entries](#2-get-all-payroll-entries)
    - [3. Get Payroll Entry by ID](#3-get-payroll-entry-by-id)
    - [4. Update Payroll Entry by ID](#4-update-payroll-entry-by-id)
    - [5. Delete Payroll Entry by ID](#5-delete-payroll-entry-by-id)
  - [Expense Section](#expense-section)
    - [1. Create New Expense Entry](#1-create-new-expense-entry)
    - [2. Get All Expense Entries](#2-get-all-expense-entries)
    - [3. Get Expense Entry by ID](#3-get-expense-entry-by-id)
    - [4. Update Expense Entry by ID](#4-update-expense-entry-by-id)
    - [5. Delete Expense Entry by ID](#5-delete-expense-entry-by-id)
    - [6. Get Expense Report](#6-get-expense-report)
    - [7. Get Date-Wise Expense Data](#7-get-date-wise-expense-data)
  - [Profit Report Section](#profit-report-section)
    - [1. Get Profit Report](#1-get-profit-report)
    - [2. Get Date-Wise Profit Data](#2-get-date-wise-profit-data)

# Admin Level

## User Section

### 1. Create New User

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/user/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new user with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "username": "admin_one",
    "password": "admin_one",
    "role": "admin"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "success": "Data uploaded successfully."
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'username', 'password' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Users

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/user/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all users.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(user)",
        "username": "admin_one",
        "password": "Hashed(password)",
        "role": "admin",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(user)",
        "username": "user_one",
        "password": "Hashed(password)",
        "role": "user",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(user)",
        "username": "manager_one",
        "password": "Hashed(password)",
        "role": "manager",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get User by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/user/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific user by ID.`
- **URL Parameters:** - `id`: User ID (Example: `/user/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(user)",
      "username": "user_one",
      "password": "Hashed(password)",
      "role": "user",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update User by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/user/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific user by ID.`
- **URL Parameters:** - `id`: User ID (Example: `/user/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "username": "updated_user",
    "password": "updated_password",
    "role": "updated_user"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(user)",
      "username": "updated_user",
      "password": "Hashed(password)",
      "role": "updated_user",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete User by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/user/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a user by ID.`
- **URL Parameters:** - `id`: User ID (Example: `/user/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Profile Section

### 1. Create New Profile

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/profile/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new profile with the provided information.`
- **Request Format:** `multipart/form-data`
  ```md
  id:ObjectID(profile)
  profileID:GeneratedID(profile)
  name:John Doe
  email:john.doe@example.com
  religion:Christian
  nationality:American
  gender:Male
  maritalStatus:Single
  birthDate:1990-01-01
  NID:123456789
  NIDPicture:Picture(NID)
  photo:Picture(photo)
  aboutMe:Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  workNumber:123456789
  personalNumber:987654321
  presentAddress:123 Main Street, City
  permanentAddress:456 Secondary Street, City
  emergencyContactName:Emergency Contact
  emergencyContactNumber:987654321
  emergencyRelation:Relative
  bankName:Bank of Example
  bankAccountNo:123456789
  bankBranch:Branch City
  department:IT
  designation:Developer
  role:Backend Developer
  location:City
  dateOfJoining:2022-01-01
  currentWorkExperience:3 years
  reportsTo:Supervisor
  salary:50000
  accommodationCost:10000
  workingHour:8
  workExperience.companyName:Example Company
  workExperience.jobTitle:Software Engineer
  workExperience.fromDate:2020-01-01
  workExperience.toDate:2022-01-01
  workExperience.description:Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  educationInfo.instituteName:Example University
  educationInfo.degreeOrDiploma:Bachelor's
  educationInfo.completeYear:2018
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "success": "Data uploaded successfully."
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'profileID', 'name', 'email', ... - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Profiles

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/profile/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all profiles.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(profile)",
        "profileID": "GeneratedID(profile)",
        "name": "John Doe",
        "email": "john.doe@example.com",
        "religion": "Christian",
        "nationality": "American",
        "gender": "Male",
        "maritalStatus": "Single",
        "birthDate": "1990-01-01",
        "NID": "123456789",
        "NIDPicture": "https://example.com/nid_picture.jpg",
        "photo": "https://example.com/photo.jpg",
        "aboutMe": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(profile)",
        "profileID": "GeneratedID(profile)",
        "name": "Jane Smith",
        "email": "jane.smith@example.com",
        "religion": "Muslim",
        "nationality": "Canadian",
        "gender": "Female",
        "maritalStatus": "Married",
        "birthDate": "1992-02-02",
        "NID": "987654321",
        "NIDPicture": "https://example.com/nid_picture.jpg",
        "photo": "https://example.com/photo.jpg",
        "aboutMe": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Profile by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/profile/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific profile by ID.`
- **URL Parameters:** - `id`: Profile ID (Example: `/profile/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(profile)",
      "profileID": "GeneratedID(profile)",
      "name": "John Doe",
      "email": "john.doe@example.com",
      "religion": "Christian",
      "nationality": "American",
      "gender": "Male",
      "maritalStatus": "Single",
      "birthDate": "1990-01-01",
      "NID": "123456789",
      "NIDPicture": "https://example.com/nid_picture.jpg",
      "photo": "https://example.com/photo.jpg",
      "aboutMe": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
      "createdAt": "Timestamp(year-month-date)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Profile by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/profile/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific profile by ID.`
- **URL Parameters:** - `id`: Profile ID (Example: `/profile/update/101`)
- **Request Format:** `multipart/form-data`
  ```json
  name:John Doe
  email:john.doe@example.com
  religion:Christian
  nationality:American
  gender:Male
  maritalStatus:Single
  birthDate:1990-01-01
  NID:123456789
  NIDPicture:Picture(NID)
  photo:Picture(photo)
  aboutMe:Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  workNumber:123456789
  personalNumber:987654321
  presentAddress:123 Main Street, City
  permanentAddress:456 Secondary Street, City
  emergencyContactName:Emergency Contact
  emergencyContactNumber:987654321
  emergencyRelation:Relative
  bankName:Bank of Example
  bankAccountNo:123456789
  bankBranch:Branch City
  department:IT
  designation:Developer
  role:Backend Developer
  location:City
  dateOfJoining:2022-01-01
  currentWorkExperience:3 years
  reportsTo:Supervisor
  salary:50000
  accommodationCost:10000
  workingHour:8
  workExperience.companyName:Example Company
  workExperience.jobTitle:Software Engineer
  workExperience.fromDate:2020-01-01
  workExperience.toDate:2022-01-01
  workExperience.description:Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  educationInfo.instituteName:Example University
  educationInfo.degreeOrDiploma:Bachelor's
  educationInfo.completeYear:2018
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Update successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Profile by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/profile/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a profile by ID.`
- **URL Parameters:** - `id`: Profile ID (Example: `/profile/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Attendance Section

### 1. Create New Attendance Record

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/attendance/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new attendance record with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "profileID": "GeneratedID(profile)",
    "name": "John Doe",
    "attendance": true
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(attendance)",
      "profileID": "GeneratedID(profile)",
      "name": "John Doe",
      "attendance": true,
      "createdAt": "Timestamp(year-month-date)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'profileID', 'name', 'attendance' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Attendance Records

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/attendance/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all attendance records.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(attendance)",
        "profileID": "GeneratedID(profile)",
        "name": "John Doe",
        "attendance": true,
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(attendance)",
        "profileID": "GeneratedID(profile)",
        "name": "Jane Smith",
        "attendance": false,
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Update Attendance Record by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/attendance/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific attendance record by ID.`
- **URL Parameters:** - `id`: Attendance Record ID (Example: `/attendance/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "profileID": "GeneratedID(update_profile)",
    "name": "Updated Name",
    "attendance": false
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(attendance)",
      "profileID": "PRO000001",
      "name": "Updated Name",
      "attendance": false,
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Delete Attendance Record by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/attendance/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes an attendance record by ID.`
- **URL Parameters:** - `id`: Attendance Record ID (Example: `/attendance/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Attendance Absent Percentage Pie Chart

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/attendance/piechart
  ```
- **Method:** `GET`
- **Description:** `Generates a pie chart with attendance statistics between specified dates.`
- **Query Parameters:**
  - `startDate` (required): Start date for the report (format: YYYY-MM-DD).
  - `endDate` (required): End date for the report (format: YYYY-MM-DD).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Report generated successfully.",
      "data": {
        "attendancePercentage": "XX.XX",
        "absentPercentage": "YY.YY"
      }
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 6. Get Date-wise Attendance Data

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/attendance/date
  ```
- **Method:** `GET`
- **Description:** `Gets date-wise attendance data between specified dates.`
- **Query Parameters:**
  - `startDate` (required): Start date for the report (format: YYYY-MM-DD).
  - `endDate` (required): End date for the report (format: YYYY-MM-DD).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Data retrieved successfully.",
      "attendanceData": [
        {
          "_date": "YYYY-MM-DD",
          "totalAttendance": X,
          "totalPresent": Y
        },
        {
          "_date": "YYYY-MM-DD",
          "totalAttendance": X,
          "totalPresent": Y
        }
      ]
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Order Section

### 1. Create New Order

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/order/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new order with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "orderName": "Order123",
    "customerName": "John Doe",
    "productCode": "P123",
    "quantity": 5,
    "deliveryDate": "2024-02-03",
    "pricePerUnit": 20.5,
    "totalAmount": 102.5,
    "paymentStatus": "Pending"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(order)",
      "orderName": "Order123",
      "customerName": "John Doe",
      "productCode": "P123",
      "quantity": 5,
      "deliveryDate": "2024-02-03T00:00:00.000Z",
      "pricePerUnit": 20.5,
      "totalAmount": 102.5,
      "paymentStatus": "Pending",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'orderName', 'customerName', 'productCode', 'quantity', 'deliveryDate', 'pricePerUnit', 'totalAmount', 'paymentStatus' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Orders

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/order/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all orders.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(order)",
        "orderName": "Order123",
        "customerName": "John Doe",
        "productCode": "P123",
        "quantity": 5,
        "deliveryDate": "2024-02-03T00:00:00.000Z",
        "pricePerUnit": 20.5,
        "totalAmount": 102.5,
        "paymentStatus": "Pending",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(order)",
        "orderName": "Order456",
        "customerName": "Jane Smith",
        "productCode": "P456",
        "quantity": 10,
        "deliveryDate": "2024-02-05T00:00:00.000Z",
        "pricePerUnit": 15.5,
        "totalAmount": 155,
        "paymentStatus": "Paid",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Order by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/order/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific order by ID.`
- **URL Parameters:** - `id`: Order ID (Example: `/order/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(order)",
      "orderName": "Order123",
      "customerName": "John Doe",
      "productCode": "P123",
      "quantity": 5,
      "deliveryDate": "2024-02-03T00:00:00.000Z",
      "pricePerUnit": 20.5,
      "totalAmount": 102.5,
      "paymentStatus": "Pending",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Order by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/order/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific order by ID.`
- **URL Parameters:** - `id`: Order ID (Example: `/order/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "orderName": "UpdatedOrder123",
    "customerName": "Updated John Doe",
    "quantity": 8,
    "deliveryDate": "2024-02-10",
    "pricePerUnit": 25.5,
    "totalAmount": 204,
    "paymentStatus": "Paid"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(order)",
      "orderName": "UpdatedOrder123",
      "customerName": "Updated John Doe",
      "productCode": "P123",
      "quantity": 8,
      "deliveryDate": "2024-02-10T00:00:00.000Z",
      "pricePerUnit": 25.5,
      "totalAmount": 204,
      "paymentStatus": "Paid",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Order by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/order/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes an order by ID.`
- **URL Parameters:** - `id`: Order ID (Example: `/order/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Sales Section

### 1. Create New Sales Entry

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new sales entry with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "date": "2024-02-03",
    "amount": 100.5,
    "description": "Product sales",
    "type": "Online",
    "clientName": "John Doe",
    "receivedPerson": "Alice",
    "directOrder": "Yes"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(sales)",
      "date": "2024-02-03T00:00:00.000Z",
      "amount": 100.5,
      "description": "Product sales",
      "type": "Online",
      "clientName": "John Doe",
      "receivedPerson": "Alice",
      "directOrder": "Yes",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'date', 'amount', 'description', 'type', 'clientName', 'receivedPerson', 'directOrder' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Sales Entries

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all sales entries.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(sales)",
        "date": "2024-02-03T00:00:00.000Z",
        "amount": 100.5,
        "description": "Product sales",
        "type": "Online",
        "clientName": "John Doe",
        "receivedPerson": "Alice",
        "directOrder": "Yes",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(sales)",
        "date": "2024-02-05T00:00:00.000Z",
        "amount": 150.5,
        "description": "Service sales",
        "type": "Offline",
        "clientName": "Jane Smith",
        "receivedPerson": "Bob",
        "directOrder": "No",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Sales Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific sales entry by ID.`
- **URL Parameters:** - `id`: Sales Entry ID (Example: `/sales/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(sales)",
      "date": "2024-02-03T00:00:00.000Z",
      "amount": 100.5,
      "description": "Product sales",
      "type": "Online",
      "clientName": "John Doe",
      "receivedPerson": "Alice",
      "directOrder": "Yes",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Sales Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific sales entry by ID.`
- **URL Parameters:** - `id`: Sales Entry ID (Example: `/sales/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "date": "2024-02-03",
    "amount": 120.5,
    "description": "Updated product sales",
    "type": "Online",
    "clientName": "Updated John Doe",
    "receivedPerson": "Updated Alice",
    "directOrder": "No"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(sales)",
      "date": "2024-02-03T00:00:00.000Z",
      "amount": 120.5,
      "description": "Updated product sales",
      "type": "Online",
      "clientName": "Updated John Doe",
      "receivedPerson": "Updated Alice",
      "directOrder": "No",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Sales Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a sales entry by ID.`
- **URL Parameters:** - `id`: Sales Entry ID (Example: `/sales/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 6. Get Sales Report

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/report
  ```
- **Method:** `GET`
- **Description:** `Generates a sales report for a specific date range.`
- **Query Parameters:**
  - `startDate` (required): Start date of the report (format: 'YYYY-MM-DD').
  - `endDate` (required): End date of the report (format: 'YYYY-MM-DD').
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Report generated successfully.",
      "data": {
        "startDate": "2024-02-01",
        "endDate": "2024-02-15",
        "totalSalesAmount": 250.5,
        "salesData": [
          {
            "id": "ObjectID(sales)",
            "date": "2024-02-03T00:00:00.000Z",
            "amount": 100.5,
            "description": "Product sales",
            "type": "Online",
            "clientName": "John Doe",
            "receivedPerson": "Alice",
            "directOrder": "Yes",
            "createdAt": "Timestamp(date-month-year)",
            "updatedAt": "Timestamp(date-month-year)"
          },
          {
            "id": "ObjectID(sales)",
            "date": "2024-02-05T00:00:00.000Z",
            "amount": 150.5,
            "description": "Service sales",
            "type": "Offline",
            "clientName": "Jane Smith",
            "receivedPerson": "Bob",
            "directOrder": "No"
            "createdAt": "Timestamp(date-month-year)",
            "updatedAt": "Timestamp(date-month-year)"
          }
        ]
      }
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Invalid date format."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 7. Get Date-wise Sales Data

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/sales/report/day
  ```
- **Method:** `GET`
- **Description:** `Gets date-wise sales data for a specific date range.`
- **Query Parameters:**
  - `startDate` (required): Start date of the report (format: 'YYYY-MM-DD').
  - `endDate` (required): End date of the report (format: 'YYYY-MM-DD').
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Data retrieved successfully.",
      "data": [
        {
          "date": "2024-02-03",
          "totalSales": 100.5,
          "count": 1
        },
        {
          "date": "2024-02-05",
          "totalSales": 150.5,
          "count": 1
        }
      ]
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Invalid date format."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Inventory Section

### 1. Create New Inventory

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/inventory/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new inventory entry with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "supplierID": "SUP000001",
    "supplierName": "ABC Suppliers",
    "price": 50.99,
    "status": "In Stock",
    "quantity": 100,
    "quality": "High",
    "purchaseDate": "2024-02-03T14:30:00.000Z",
    "receivedPerson": "John Doe",
    "description": "High-quality raw materials for production."
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(inventory)",
      "supplierID": "SUP000001",
      "supplierName": "ABC Suppliers",
      "price": 50.99,
      "status": "In Stock",
      "quantity": 100,
      "quality": "High",
      "purchaseDate": "2024-02-03T14:30:00.000Z",
      "receivedPerson": "John Doe",
      "description": "High-quality raw materials for production.",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'supplierID', 'supplierName', 'price', 'status', 'quantity', 'quality', 'purchaseDate', 'receivedPerson', 'description' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Inventory Items

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/inventory/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all inventory items.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(inventory)",
        "supplierID": "SUP000001",
        "supplierName": "ABC Suppliers",
        "price": 50.99,
        "status": "In Stock",
        "quantity": 100,
        "quality": "High",
        "purchaseDate": "2024-02-03T14:30:00.000Z",
        "receivedPerson": "John Doe",
        "description": "High-quality raw materials for production.",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(inventory)",
        "supplierID": "SUP000002",
        "supplierName": "XYZ Suppliers",
        "price": 35.5,
        "status": "Out of Stock",
        "quantity": 50,
        "quality": "Medium",
        "purchaseDate": "2024-02-03T12:45:00.000Z",
        "receivedPerson": "Jane Doe",
        "description": "Medium-quality components for assembly.",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Inventory Item by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/inventory/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific inventory item by ID.`
- **URL Parameters:** - `id`: Inventory Item ID (Example: `/inventory/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(inventory)",
      "supplierID": "SUP000001",
      "supplierName": "ABC Suppliers",
      "price": 50.99,
      "status": "In Stock",
      "quantity": 100,
      "quality": "High",
      "purchaseDate": "2024-02-03T14:30:00.000Z",
      "receivedPerson": "John Doe",
      "description": "High-quality raw materials for production.",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Inventory Item by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/inventory/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific inventory item by ID.`
- **URL Parameters:** - `id`: Inventory Item ID (Example: `/inventory/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "supplierID": "SUP000002",
    "supplierName": "ABC Suppliers",
    "price": 55.5,
    "status": "Low Stock",
    "quantity": 120,
    "quality": "Updated High",
    "purchaseDate": "2024-02-03T16:00:00.000Z",
    "receivedPerson": "Updated John Doe",
    "description": "Updated description."
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(inventory)",
      "supplierID": "SUP000002",
      "supplierName": "ABC Suppliers",
      "price": 55.5,
      "status": "Low Stock",
      "quantity": 120,
      "quality": "Updated High",
      "purchaseDate": "2024-02-03T16:00:00.000Z",
      "receivedPerson": "Updated John Doe",
      "description": "Updated description.",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Inventory Item by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/inventory/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a specific inventory item by ID.`
- **URL Parameters:** - `id`: Inventory Item ID (Example: `/inventory/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Supplier Section

### 1. Create New Supplier

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/supplier/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new supplier entry with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "supplierID": "SUP000001",
    "name": "ABC Supplier",
    "address": "123 Supplier Street",
    "contactNumber": "123-456-7890",
    "type": "Material",
    "description": "Primary supplier for raw materials"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(supplier)",
      "supplierID": "SUP000001",
      "name": "ABC Supplier",
      "address": "123 Supplier Street",
      "contactNumber": "123-456-7890",
      "type": "Material",
      "description": "Primary supplier for raw materials",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'supplierID', 'name', 'address', 'contactNumber', 'type', 'description' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Suppliers

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/supplier/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all supplier entries.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(supplier)",
        "supplierID": "SUP000001",
        "name": "ABC Supplier",
        "address": "123 Supplier Street",
        "contactNumber": "123-456-7890",
        "type": "Material",
        "description": "Primary supplier for raw materials",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(supplier)",
        "supplierID": "SUP000002",
        "name": "XYZ Supplier",
        "address": "456 Supplier Street",
        "contactNumber": "987-654-3210",
        "type": "Equipment",
        "description": "Supplier for machinery",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Supplier by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/supplier/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific supplier entry by ID.`
- **URL Parameters:** - `id`: Supplier Entry ID (Example: `/supplier/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(supplier)",
      "supplierID": "SUP000001",
      "name": "ABC Supplier",
      "address": "123 Supplier Street",
      "contactNumber": "123-456-7890",
      "type": "Material",
      "description": "Primary supplier for raw materials",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Supplier by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/supplier/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific supplier entry by ID.`
- **URL Parameters:** - `id`: Supplier Entry ID (Example: `/supplier/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "supplierID": "SUP000001",
    "name": "Updated ABC Supplier",
    "address": "Updated 123 Supplier Street",
    "contactNumber": "123-456-7890",
    "type": "Material",
    "description": "Updated primary supplier for raw materials"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(supplier)",
      "supplierID": "SUP000001",
      "name": "Updated ABC Supplier",
      "address": "Updated 123 Supplier Street",
      "contactNumber": "123-456-7890",
      "type": "Material",
      "description": "Updated primary supplier for raw materials",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Supplier by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/supplier/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a supplier entry by ID.`
- **URL Parameters:** - `id`: Supplier Entry ID (Example: `/supplier/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Production Section

### 1. Create New Production

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/production/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new production entry with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "supervisor": "John Doe",
    "itemName": "Product XYZ",
    "workType": "Assembly",
    "outputQuantity": 100,
    "lastEntryTime": "2024-02-03T12:30:00.000Z",
    "expectedOutputQuantity": 150,
    "status": "In Progress"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(production)",
      "supervisor": "John Doe",
      "itemName": "Product XYZ",
      "workType": "Assembly",
      "outputQuantity": 100,
      "lastEntryTime": "2024-02-03T12:30:00.000Z",
      "expectedOutputQuantity": 150,
      "status": "In Progress",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'supervisor', 'itemName', 'workType', 'outputQuantity', 'lastEntryTime', 'expectedOutputQuantity', 'status' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Productions

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/production/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all production entries.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(production)",
        "supervisor": "John Doe",
        "itemName": "Product XYZ",
        "workType": "Assembly",
        "outputQuantity": 100,
        "lastEntryTime": "2024-02-03T12:30:00.000Z",
        "expectedOutputQuantity": 150,
        "status": "In Progress",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(production)",
        "supervisor": "Jane Doe",
        "itemName": "Product ABC",
        "workType": "Manufacturing",
        "outputQuantity": 50,
        "lastEntryTime": "2024-02-03T11:45:00.000Z",
        "expectedOutputQuantity": 100,
        "status": "Completed",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Production by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/production/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific production entry by ID.`
- **URL Parameters:** - `id`: Production Entry ID (Example: `/production/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(production)",
      "supervisor": "John Doe",
      "itemName": "Product XYZ",
      "workType": "Assembly",
      "outputQuantity": 100,
      "lastEntryTime": "2024-02-03T12:30:00.000Z",
      "expectedOutputQuantity": 150,
      "status": "In Progress",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Production by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/production/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific production entry by ID.`
- **URL Parameters:** - `id`: Production Entry ID (Example: `/production/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "supervisor": "Updated John Doe",
    "itemName": "Updated Product XYZ",
    "workType": "Updated Assembly",
    "outputQuantity": 120,
    "lastEntryTime": "2024-02-03T14:45:00.000Z",
    "expectedOutputQuantity": 150,
    "status": "In Progress"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(production)",
      "supervisor": "Updated John Doe",
      "itemName": "Updated Product XYZ",
      "workType": "Updated Assembly",
      "outputQuantity": 120,
      "lastEntryTime": "2024-02-03T14:45:00.000Z",
      "expectedOutputQuantity": 150,
      "status": "In Progress",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Production by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/production/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a production entry by ID.`
- **URL Parameters:** - `id`: Production Entry ID (Example: `/production/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>


## Overtime Section

### 1. Create New Overtime Entry

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/overtime/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new overtime entry with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "profileID": "PRO000001",
    "profileName": "John Doe",
    "date": "2024-02-03",
    "perHour": 15.5,
    "salary": 1500,
    "workingHour": 8,
    "overTimeHour": "2"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(overtime)",
      "profileID": "PRO000001",
      "profileName": "John Doe",
      "date": "2024-02-03",
      "perHour": 15.5,
      "salary": 1500,
      "workingHour": 8,
      "overTimeHour": "2",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'profileID', 'profileName', 'date', 'perHour', 'salary', 'workingHour', 'overTimeHour' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Overtime Entries

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/overtime/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all overtime entries.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(overtime)",
        "profileID": "PRO000001",
        "profileName": "John Doe",
        "date": "2024-02-03",
        "perHour": 15.5,
        "salary": 1500,
        "workingHour": 8,
        "overTimeHour": "2",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(overtime)",
        "profileID": "PRO000002",
        "profileName": "Jane Doe",
        "date": "2024-02-04",
        "perHour": 20.0,
        "salary": 2000,
        "workingHour": 8,
        "overTimeHour": "3",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Overtime Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/overtime/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific overtime entry by ID.`
- **URL Parameters:** - `id`: Overtime Entry ID (Example: `/overtime/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(overtime)",
      "profileID": "PRO000001",
      "profileName": "John Doe",
      "date": "2024-02-03",
      "perHour": 15.5,
      "salary": 1500,
      "workingHour": 8,
      "overTimeHour": "2",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Overtime Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/overtime/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific overtime entry by ID.`
- **URL Parameters:** - `id`: Overtime Entry ID (Example: `/overtime/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "profileID": "PRO000002",
    "profileName": "Updated John Doe",
    "date": "2024-02-04",
    "perHour": 18.0,
    "salary": 1800,
    "workingHour": 8,
    "overTimeHour": "3"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(overtime)",
      "profileID": "Updated 12345",
      "profileName": "Updated John Doe",
      "date": "2024-02-04",
      "perHour": 18.0,
      "salary": 1800,
      "workingHour": 8,
      "overTimeHour": "3",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Overtime Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/overtime/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a specific overtime entry by ID.`
- **URL Parameters:** - `id`: Overtime Entry ID (Example: `/overtime/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Payroll Section

### 1. Create New Payroll Entry

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/payroll/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new payroll entry with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "profileID": "PRO000001",
    "profileName": "John Doe",
    "perHour": 15.5,
    "basicSalary": 1500,
    "overtimeSalary": 200,
    "totalSalary": 1700
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(payroll)",
      "profileID": "PRO000001",
      "profileName": "John Doe",
      "perHour": 15.5,
      "basicSalary": 1500,
      "overtimeSalary": 200,
      "totalSalary": 1700,
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Input errors: 'profileID', 'profileName', 'perHour', 'basicSalary', 'overtimeSalary', 'totalSalary' - required"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Payroll Entries

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/payroll/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all payroll entries.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(payroll)",
        "profileID": "PRO000001",
        "profileName": "John Doe",
        "perHour": 15.5,
        "basicSalary": 1500,
        "overtimeSalary": 200,
        "totalSalary": 1700,
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(payroll)",
        "profileID": "PRO000002",
        "profileName": "Jane Doe",
        "perHour": 18.0,
        "basicSalary": 1800,
        "overtimeSalary": 250,
        "totalSalary": 2050,
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Payroll Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/payroll/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific payroll entry by ID.`
- **URL Parameters:** - `id`: Payroll Entry ID (Example: `/payroll/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(payroll)",
      "profileID": "PRO000001",
      "profileName": "John Doe",
      "perHour": 15.5,
      "basicSalary": 1500,
      "overtimeSalary": 200,
      "totalSalary": 1700,
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Payroll Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/payroll/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific payroll entry by ID.`
- **URL Parameters:** - `id`: Payroll Entry ID (Example: `/payroll/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "profileID": "Updated 12345",
    "profileName": "Updated John Doe",
    "perHour": 18.0,
    "basicSalary": 1800,
    "overtimeSalary": 250,
    "totalSalary": 2050
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(payroll)",
      "profileID": "Updated 12345",
      "profileName": "Updated John Doe",
      "perHour": 18.0,
      "basicSalary": 1800,
      "overtimeSalary": 250,
      "totalSalary": 2050,
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Payroll Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/payroll/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a specific payroll entry by ID.`
- **URL Parameters:** - `id`: Payroll Entry ID (Example: `/payroll/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Expense Section

### 1. Create New Expense Entry

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/create
  ```
- **Method:** `POST`
- **Description:** `Creates a new expense entry with the provided information.`
- **Request Format:** `multipart/form-data`
  ```md
  title:Office Supplies
  description:Purchase of office supplies
  type:Office
  amount:200.0
  usageUnit:1
  date:2024-02-01
  status:Pending
  receiptPicture:Picture(receipt)
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(expense)",
      "title": "Office Supplies",
      "description": "Purchase of office supplies",
      "type": "Office",
      "amount": 200.0,
      "usageUnit": 1,
      "date": "2024-02-01T00:00:00.000Z",
      "status": "Pending",
      "receiptPicture": "https://example.com/recipt.jpg",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "File missing or upload error."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get All Expense Entries

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/find/all
  ```
- **Method:** `GET`
- **Description:** `Gets a list of all expense entries.`
- **Query Parameters:**
  - `limit` (optional): Number of records to retrieve per load (default: 15).
  - `skip` (optional): Number of records to skip for subsequent loads (default: 0).
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(expense)",
        "title": "Office Supplies",
        "description": "Purchase of office supplies",
        "type": "Office",
        "amount": 200.0,
        "usageUnit": 1,
        "date": "2024-02-01T00:00:00.000Z",
        "status": "Pending",
        "receiptPicture": "https://example.com/recipt.jpg",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      },
      {
        "id": "ObjectID(expense)",
        "title": "Travel Expenses",
        "description": "Travel reimbursement",
        "type": "Travel",
        "amount": 150.0,
        "usageUnit": 1,
        "date": "2024-02-02T00:00:00.000Z",
        "status": "Approved",
        "receiptPicture": "https://example.com/recipt.jpg",
        "createdAt": "Timestamp(date-month-year)",
        "updatedAt": "Timestamp(date-month-year)"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Expense Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/find/:id
  ```
- **Method:** `GET`
- **Description:** `Gets information about a specific expense entry by ID.`
- **URL Parameters:** - `id`: Expense Entry ID (Example: `/expense/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(expense)",
      "title": "Office Supplies",
      "description": "Purchase of office supplies",
      "type": "Office",
      "amount": 200.0,
      "usageUnit": 1,
      "date": "2024-02-01T00:00:00.000Z",
      "status": "Pending",
      "receiptPicture": "https://example.com/recipt.jpg",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Expense Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/update/:id
  ```
- **Method:** `PUT`
- **Description:** `Updates information for a specific expense entry by ID.`
- **URL Parameters:** - `id`: Expense Entry ID (Example: `/expense/update/101`)
- **Request Format:** `multipart/form-data`
  ```md
  title:Office Supplies
  description:Purchase of office supplies
  type:Office
  amount:200.0
  usageUnit:1
  date:2024-02-01
  status:Pending
  receiptPicture:Picture(receipt)
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(expense)",
      "title": "Updated Office Supplies",
      "description": "Updated purchase of office supplies",
      "type": "Office",
      "amount": 250.0,
      "usageUnit": 1,
      "date": "2024-02-03T00:00:00.000Z",
      "status": "Pending",
      "receiptPicture": "https://example.com/recipt.jpg",
      "createdAt": "Timestamp(date-month-year)",
      "updatedAt": "Timestamp(date-month-year)"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete Expense Entry by ID

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/delete/:id
  ```
- **Method:** `DELETE`
- **Description:** `Deletes a specific expense entry by ID.`
- **URL Parameters:** - `id`: Expense Entry ID (Example: `/expense/delete/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Delete successful."
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Data not found."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 6. Get Expense Report

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/report
  ```
- **Method:** `GET`
- **Description:** `Generates an expense report based on the specified date range.`
- **Query Parameters:**
  - `startDate` (required): Start date in 'YYYY-MM-DD' format.
  - `endDate` (required): End date in 'YYYY-MM-DD' format.
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Operation successful",
      "data": {
        "startDate": "2024-02-01T00:00:00.000Z",
        "endDate": "2024-02-03T23:59:59.999Z",
        "total": 600.0,
        "expenses": [
          {
            "id": "ObjectID(expense)",
            "title": "Office Supplies",
            "description": "Purchase of office supplies",
            "type": "Office",
            "amount": 200.0,
            "usageUnit": 1,
            "date": "2024-02-01T00:00:00.000Z",
            "status": "Pending",
            "receiptPicture": "https://example.com/recipt.jpg",
            "createdAt": "Timestamp(date-month-year)",
            "createdAt": "Timestamp(date-month-year)",
            "updatedAt": "Timestamp(date-month-year)"
          },
          {
            "id": "ObjectID(expense)",
            "title": "Travel Expenses",
            "description": "Travel reimbursement",
            "type": "Travel",
            "amount": 150.0,
            "usageUnit": 1,
            "date": "2024-02-02T00:00:00.000Z",
            "status": "Approved",
            "receiptPicture": "https://example.com/recipt.jpg",
            "createdAt": "Timestamp(date-month-year)",
            "createdAt": "Timestamp(date-month-year)",
            "updatedAt": "Timestamp(date-month-year)"
          },
          {
            "id": "ObjectID(expense)",
            "title": "Updated Office Supplies",
            "description": "Updated purchase of office supplies",
            "type": "Office",
            "amount": 250.0,
            "usageUnit": 1,
            "date": "2024-02-03T00:00:00.000Z",
            "status": "Pending",
            "receiptPicture": "https://example.com/recipt.jpg",
            "createdAt": "Timestamp(date-month-year)",
            "updatedAt": "Timestamp(date-month-year)"
          }
        ]
      }
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Invalid date format."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 7. Get Date-Wise Expense Data

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/expense/report/day
  ```
- **Method:** `GET`
- **Description:** `Gets date-wise expense data for the specified date range.`
- **Query Parameters:**
  - `startDate` (required): Start date in 'YYYY-MM-DD' format.
  - `endDate` (required): End date in 'YYYY-MM-DD' format.
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Operation successful",
      "data": [
        {
          "totalExpenses": 200.0,
          "count": 1,
          "_date": "2024-02-01"
        },
        {
          "totalExpenses": 150.0,
          "count": 1,
          "_date": "2024-02-02"
        },
        {
          "totalExpenses": 250.0,
          "count": 1,
          "_date": "2024-02-03"
        }
      ]
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Invalid date format."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Profit Report Section

### 1. Get Profit Report

- **Endpoint:**
  ```md
  143.110.190.164:3004/admin/profit/report
  ```
- **Method:** `GET`
- **Description:** `Generates a profit report based on the specified date range.`
- **Query Parameters:**
  - `startDate` (required): Start date in 'YYYY-MM-DD' format.
  - `endDate` (required): End date in 'YYYY-MM-DD' format.
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Data retrieved successfully",
      "data": {
        "startDate": "2024-02-01T00:00:00.000Z",
        "endDate": "2024-02-03T23:59:59.999Z",
        "totalSales": 600.0,
        "totalExpenses": 300.0,
        "totalInventoryCost": 150.0,
        "profit": 150.0
      }
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Invalid date format."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 2. Get Date-Wise Profit Data

- **Endpoint:** 
  ```md
  143.110.190.164:3004/admin/profit/report/date
  ```
- **Method:** `GET`
- **Description:** `Gets date-wise profit data for the specified date range.`
- **Query Parameters:**
  - `startDate` (required): Start date in 'YYYY-MM-DD' format.
  - `endDate` (required): End date in 'YYYY-MM-DD' format.
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "success": "Data retrieved successfully",
      "data": [
        {
          "_date": "2024-02-01",
          "totalSales": 200.0,
          "totalExpenses": 100.0,
          "profit": 100.0
        },
        {
          "_date": "2024-02-02",
          "totalSales": 150.0,
          "totalExpenses": 50.0,
          "profit": 100.0
        },
        {
          "_date": "2024-02-03",
          "totalSales": 250.0,
          "totalExpenses": 150.0,
          "profit": 100.0
        }
      ]
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Invalid date format."
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>
