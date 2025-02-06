# rental-booking-system
CREATE TABLE cars (
    id INT AUTO_INCREMENT PRIMARY KEY,
    make VARCHAR(100) NOT NULL,
    model VARCHAR(100) NOT NULL,
    year INT NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    availability BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

customers Table
Holds user details for the application.


CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    phone VARCHAR(15) NOT NULL,
    address TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
bookings Table
Tracks car reservations.



CREATE TABLE bookings (
    id INT AUTO_INCREMENT PRIMARY KEY,
    car_id INT NOT NULL,
    customer_id INT NOT NULL,
    start_date DATE NOT NULL,
    end_date DATE NOT NULL,
    total_price DECIMAL(10, 2) NOT NULL,
    status ENUM('booked', 'completed', 'cancelled') DEFAULT 'booked',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (car_id) REFERENCES cars(id) ON DELETE CASCADE,
    FOREIGN KEY (customer_id) REFERENCES customers(id) ON DELETE CASCADE
);
Project Structure 🗂️
css
Copy code
online-car-dealership/
├── src/
│   └── com/
│       └── cardealership/
│           ├── Car.java
│           ├── CarDAO.java
│           ├── InventoryDAO.java
│           └── DBConnection.java
├── lib/
│   └── mysql-connector-java-x.x.x.jar (MySQL JDBC Driver)
├── assets/
│   └── database-connection-success.png
├── .gitignore
├── README.md
└── Main.java

🛠️ Project Structure

UserManagementTemplate/  
├── index.html                # Home Page (Dashboard)  
├── users.html                # User List Page  
├── add-user.html             # Add New User Form  
├── edit-user.html            # Edit User Form  
├── assets/  
│   ├── css/  
│   │   ├── styles.css        # Custom Styles  
│   └── js/  
│       ├── script.js         # Custom Scripts  
└── README.md                 # Project Documentation  
Review 2
HTML Pages Created:

Designed index.html with a dashboard-style layout.
Built the users.html page to display a list of users in a tabular format.
Added add-user.html and edit-user.html for user form functionalities.
Styling and Layout:

Applied Bootstrap for grid layout and responsive design.
Customized
Technologies Used 🚀
Java (JDK): Backend development and logic.
JDBC: Database connectivity.
MySQL: Database storage and management.
HTML, CSS, JavaScript: Frontend design and functionality.
MySQL JDBC Driver: Connects Java to MySQL.
VS Code: Development environment.
Maven: Dependency management.
Relationships 🔗
One-to-Many between cars and bookings: A car can have multiple bookings.
One-to-Many between customers and bookings: A customer can make multiple bookings.
Cascade Deletes: Deleting a car or customer removes associated bookings automatically.
Contributing ✨
Feel free to contribute by forking this repository and creating a pull request with your improvements or bug fixes.

This project demonstrates expertise in full-stack development, database management, and front-end design. It is scalable for future enhancements like payment gateways and automated notifications, making it a robust example of a real-world web application.

![Alt Text](![Alt text](<Screenshot 2024-12-03 224020.png>))
![Alt Text](![Alt text](<Screenshot 2024-12-03 224020-1.png>))








