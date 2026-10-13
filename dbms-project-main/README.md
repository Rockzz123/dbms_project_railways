# 🚆 Indian Railway Reservation System  

[![Database MySQL](https://img.shields.io/badge/Database-MySQL-blue?logo=mysql)](#tech-stack)

An advanced **database-driven railway reservation management system** built using **MySQL**.  
This project handles **passenger bookings, train schedules, seat allocation, payments, cancellations, and feedback** efficiently, following proper **database normalization** and optimized **stored procedures**.

---

## 📌 Table of Contents  
- [Overview](#-overview)  
- [Features](#-features)  
- [Tech Stack](#-tech-stack)  
- [Database Design](#-database-design)  
- [Key Procedures & Triggers](#-key-procedures--triggers)  
- [Setup Instructions](#-setup-instructions)  
- [Usage](#-usage)  
- [Future Enhancements](#-future-enhancements)  
- [Contributors](#-contributors)  

---

## 🚀 Overview  
The **Indian Railway Reservation System** is designed to manage:  
- Passenger bookings & cancellations  
- Train schedules & routes  
- Real-time seat allocation  
- Payment processing & refunds  
- Feedback collection  
- PNR tracking & reporting  

The system ensures **data consistency** and **high performance** using **MySQL procedures, triggers, and views**.

---

## ✨ Features  

✅ **Passenger Management** – Add, update, and manage passenger details  
✅ **Booking & PNR Generation** – Handles ticket booking, confirmation, and waiting lists  
✅ **Seat Allocation** – Automatically assigns seats based on availability  
✅ **Payment & Refunds** – Integrated payment handling with refund tracking  
✅ **PNR Tracking** – Check booking and seat status  
✅ **Cancellation System** – Auto-refunds and seat release  
✅ **Feedback Module** – Collects ratings and complaints  
✅ **Optimized Queries** – Fast access to routes, availability, and schedules  

---

## 🛠 Tech Stack  

| Technology   | Purpose |
|-------------|--------------------------------|
| ![MySQL](https://img.shields.io/badge/Database-MySQL-blue?logo=mysql) | Database & Stored Procedures |
| **Triggers** | Automatic updates on booking, cancellations & payments |
| **Views**    | For analytics & reporting |
| **ERD**      | Well-structured schema |
| **Normalization** | Applied up to **3NF** |

---

## 🗄 Database Design  

The project consists of **13 core tables**:  

- **Station** – Stores station details  
- **Train** – Train info & type  
- **Route** – Route details with timings  
- **Schedule** – Train schedules  
- **Class** – Coach classes with fares  
- **Coach** – Coach information  
- **Seat** – Seat mapping & availability  
- **Passenger** – Passenger records  
- **Booking** – Ticket bookings & statuses  
- **SeatAllocation** – Seat allocation after booking  
- **Payment** – Payment & refund info  
- **Feedback** – Passenger feedback  
- **BookingStatus** – Status tracking  

📌 **Normalization Applied:**  
- **1NF** → Atomic fields ✅  
- **2NF** → Removed partial dependencies ✅  
- **3NF** → No transitive dependencies ✅  

---

## 🔧 Key Procedures & Triggers  

### **Stored Procedures**  
- `BookTicket()` → Books a ticket, calculates fare, generates itemized bill  
- `MakePayment()` → Processes payment and confirms booking  
- `CancelTicket()` → Cancels booking and processes refunds  
- `PNRTracking()` → Fetches booking and seat status  
- `AvailableSeats()` → Shows available seats per class, train, and date  
- `PassengerList()` → Lists passengers per train/date  
- `RevenueGenerated()` → Calculates total revenue  
- `ScheduleLookup()` → Returns train schedules and routes  

### **Triggers**  
- **after_booking_insert** → Inserts booking details into **SeatAllocation** automatically  
- **after_booking_cancel** → Handles seat release and refunds on cancellation  

---

## ⚡ Setup Instructions  

### **1. Clone the Repository**  
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

### **2. Import Database**  
- Open **MySQL Workbench** or **phpMyAdmin**  
- Import the `railway_reservation.sql` file  

### **3. Configure Connection**  
Update the database credentials in your project if needed:  
```ini
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=railway_reservation
```

### **4. Run the Project**  
Use your preferred SQL client or integrate it into a backend.

---

## 📌 Usage Examples  

### **Book a Ticket**
```sql
CALL BookTicket(
  1,  -- Passenger ID
  2,  -- Train ID
  101, -- Schedule ID
  '2025-09-20', -- Journey Date
  12, -- Source Station
  25, -- Destination Station
  3,  -- Class ID
  'General' -- Quota
);
```

### **Check Available Seats**
```sql
CALL availseats(2, '2025-09-20', 3);
```

### **Cancel a Ticket**
```sql
CALL cancel(1005);
```

---

## 🔮 Future Enhancements  
- ✅ Integrate a **React + Node.js frontend**  
- ✅ Add **live train tracking**  
- ✅ Implement **AI-powered seat predictions**  
- ✅ Introduce **dynamic pricing based on demand**  

---

## 👨‍💻 Contributors  

| Name | Roll Number | Contribution |
|------|------------|-------------|
| Pitta Tanuj | 2301AI29 | DB Design & Procedures |
| Member 2 | 2301AI54 | Triggers & Booking Module |
| Member 3 | 2301CS32 | Payment & Refunds |
| Member 4 | 2301CS64 | Seat Allocation & Reporting |

---

## 🖼 Project Preview  

![ERD](https://upload.wikimedia.org/wikipedia/commons/8/8d/Database_ERD_example.png)
