# 📚 bookstore-cs519-final  

A simple, PHP‑based online bookstore that demonstrates core e‑commerce functionalities such as product management, order handling, user reviews, and email notifications. The project is structured for easy learning and rapid prototyping.

---

## Overview  

The application provides two distinct interfaces:  

* **Admin panel** – Manage categories, products, orders, complaints, and reviews.  
* **Buyer side** – Browse books, place orders, and receive email confirmations via PHPMailer.

All data is stored in a MySQL database (`Database/books_db.sql`). The project was created as a final assignment for CS519.

---

## Features  

| Admin | Buyer |
|-------|-------|
| Secure login (`admin_login.php`) | Browse books |
| Add / edit / delete categories (`admin_category.php`, `edit_category.php`) | Add items to cart |
| Add / edit / delete products (`add_product.php`, `edit_product.php`) | Checkout with email receipt |
| View & export order reports (`order_report.php`) | Submit product reviews |
| Update order status (`update_order_status.php`) | View product reviews |
| Manage user accounts (`admin_user.php`) | Contact support (via PHPMailer) |
| View complaints (`view_complaints.php`) |  |
| Logout (`logout.php`) |  |

---

## Tech Stack  

| Layer | Technology |
|-------|------------|
| **Backend** | PHP 7.4+ |
| **Database** | MySQL (SQL dump in `Database/books_db.sql`) |
| **Email** | PHPMailer (included under `buyer/PHPMailer/`) |
| **Styling** | Custom CSS (`admin/css/style.css`) |
| **Documentation** | Project description (`Project file.docx`) |

---

## Installation  

1. **Clone the repository**  

   ```bash
   git clone https://github.com/your-username/bookstore-cs519-final.git
   cd bookstore-cs519-final
   ```

2. **Set up the database**  

   ```bash
   # Create a new database (e.g., books_db) in MySQL
   mysql -u root -p
   CREATE DATABASE books_db;
   EXIT;
   
   # Import the schema and sample data
   mysql -u root -p books_db < Database/books_db.sql
   ```

3. **Configure the application**  

   Edit `admin/config.php` and update the following placeholders with your own values:

   ```php
   // Database credentials
   define('DB_HOST', 'YOUR_DB_HOST');
   define('DB_NAME', 'books_db');
   define('DB_USER', 'YOUR_DB_USERNAME');
   define('DB_PASS', 'YOUR_DB_PASSWORD');

   // PHPMailer SMTP settings
   define('SMTP_HOST', 'YOUR_SMTP_HOST');
   define('SMTP_USER', 'YOUR_SMTP_USERNAME');
   define('SMTP_PASS', 'YOUR_SMTP_PASSWORD');
   define('SMTP_PORT', 587); // or 465 for SSL
   ```

4. **Install PHPMailer dependencies (optional)**  

   If you prefer Composer-managed dependencies, run:

   ```bash
   cd buyer/PHPMailer
   composer install
   ```

   *The bundled PHPMailer files are already functional, so this step is optional.*

5. **Set up a web server**  

   - Place the project inside your web root (e.g., `htdocs` for XAMPP or `www` for WAMP).  
   - Ensure the `admin/` and `buyer/` directories are accessible via HTTP.  
   - Enable