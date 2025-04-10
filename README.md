# Order Management System - iOS App

## 1. Overview

The Order Management System is an iOS application designed to help users manage their orders efficiently. It allows users to create, view, edit, and delete orders with details such as order number, due date, customer info, and order total.

---

## 2. Architecture

The app follows the MVC (Model-View-Controller) architecture:
- **Models**: Core Data entities (User, Order)
- **Views**: Custom UI like `OrderTableViewCell`
- **Controllers**: ViewControllers managing UI & logic
- **Helpers**: `CoreDataManager`, `UserManager`, `Validator`

---

## 3. Core Components

### 3.1 Data Model

**User Entity**
- `username`: String
- `password`: String
- `rememberMe`: Bool
- `orders`: [Order] (relationship)

**Order Entity**
- `orderNumber`: String
- `dueDate`: Date
- `buyerName`: String
- `address`: String
- `phone`: String
- `total`: Double
- `user`: User (relationship)

### 3.2 View Controllers

- **LoginViewController** – Authenticates user
- **RegisterViewController** – User signup + validation
- **OrdersViewController** – List, add, edit, delete orders
- **OrderDetailViewController** – Form to edit/create orders

### 3.3 Helper Classes

- `UserManager` – Session handling
- `CoreDataManager` – All CRUD logic for Core Data
- `Validator` – Input validation

### 3.4 Custom Views

- `OrderTableViewCell` – Displays order card w/ delete/edit actions

---

## 4. User Flow

### 4.1 Authentication

- App opens and checks login state
- If logged in → Orders screen
- If not → Login screen
- Login uses Core Data validation
- "Remember Me" stores user in `UserDefaults`
- Register creates a new User record

### 4.2 Order Management

- Users can:
  - View orders in table
  - Add orders using "+" or bottom button
  - Edit existing orders with pre-filled data
  - Delete with confirmation
- Orders are linked to user and persist via Core Data

---

## 5. UI Design

### 5.1 Navigation
- `UINavigationController` stack
- Large titles, back buttons

### 5.2 Order List
- Card-style table view
- Total orders count in header
- Swipe to edit/delete

### 5.3 Order Detail
- Form with validation
- Save/Cancel options
- Date Picker for due date

---

## 6. Data Persistence

- All data stored using Core Data
- Session managed with `UserDefaults`
- No external APIs used

---

## 7. Error Handling

- Validates all form inputs
- Displays messages for invalid data
- Confirmation before delete
- Success messages on save

---

## 8. Future Enhancements

- Search & filter orders
- Add status fields
- Customer management module
- Reporting & charts
- Offline mode sync
- Multi-language support

---

## 9. Technical Specs

- iOS 13.0+
- Swift 5+
- Xcode 12+
- UIKit (Programmatic UI)
- Core Data

---

> 👨‍💻 Developed for the iProTechs iOS Assessment
