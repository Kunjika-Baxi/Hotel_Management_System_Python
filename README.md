# Hotel Management System

A **Python + MySQL based management system** for hostel operations.  
It provides both **Admin** and **Guest** portals to handle room bookings, restaurant/bar orders, and billing in a unified way.

---

## Features

###  Admin Portal
- Secure login.
- Manage rooms:
  - Add new rooms with type, capacity, charges, and status.
  - Update room charges (by room number or type).
  - Delete rooms.
- View all bookings with detailed guest information.
- Manage menus:
  - Add items to **Restaurant** menu.
  - Add items to **Bar** menu.

### Guest Portal
- Login using **Booking ID**.
- Check available rooms.
- Book a room:
  - Enter personal details, dates, and room choice.
  - System calculates stay duration and charges.
  - Generates a **Booking ID** and initializes a bill.
- Cancel room booking (updates room status back to available).
- Order food from **Restaurant** or drinks from **Bar**:
  - Displays menu with prices.
  - Allows multiple orders.
  - Updates bill dynamically.
- Display consolidated bill:
  - Room charges, restaurant charges, bar charges.
  - Total amount calculated and updated in `bill` table.

---

##  Database Schema

- **rooms**: room_no, room_type, capacity, charges, room_status  
- **booking**: booking_id, name, contact, email, address, no_of_person, room_no, check_in, check_out, bill_amount  
- **restaurant**: item_no, item_name, price  
- **res_order**: order_id, booking_id (FK), item_no (FK), qty  
- **bar**: bitem_no, bitem_name, bprice  
- **bar_order**: border_id, booking_id (FK), bitem_no (FK), bqty  
- **bill**: bill_id, booking_id (FK), room_charge, res_charge, bar_charge, total_amt  

---

## Tech Stack

- **Backend:** Python (`mysql.connector`)  
- **Database:** MySQL (`Taj_db`)  
- **Modules:** `datetime` for date calculations  
- **Interface:** CLI (Command Line Interface)
1. Install MySQL and create database:
   ```sql
   CREATE DATABASE Taj_db;
