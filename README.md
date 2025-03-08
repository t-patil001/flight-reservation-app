# Flight-Reservation-App
Flight Reservation App by Cloudblitz | Greamio Technologies Pvt Ltd

## Overview
The **Flight Reservation System** is a web application that allows users to search for flights, book tickets, and manage their reservations. This application is built using Java (Spring Boot) for the backend and MySQL as the database.

## Features
- ✅ User authentication and authorization
- ✈️ Flight search and booking
- 🛠️ Admin dashboard for flight management

## Prerequisites
Before setting up the application, ensure you have the following installed on your system:

- **🖥️ Ubuntu/Linux Environment**
- **🗄️ MySQL Server**
- **☕ OpenJDK 17**
- **🛠️ Maven**
- **📂 Git**
- **🌐 Node.js and npm**
- **🌍 Apache2 Web Server**

## Clone the Repository
```sh
git clone https://github.com/shubhamkalsait/flight-reservation-app.git
```

## Database Setup Instructions

### Step 1: Update Package List
```sh
apt update
```

### Step 2: Install MySQL Server
```sh
apt install mysql-server -y
```

### Step 3: Secure MySQL Installation
```sh
mysql_secure_installation
```

### Step 4: Login to MySQL and Create Database 
```sh
mysql -uroot -p
>> CREATE DATABASE flightdb;
>> CREATE USER "DBUSER" IDENTIFIED BY "DBPASSWORD";
>> GRANT ALL PRIVILEGES ON flightdb.* TO "DBUSER";
>> FLUSH PRIVILEGES;
```

### Step 5: Import Database
```sh
cd flight-reservation-app/
mysql -uroot -p flightdb < flightdb.sql
```

## Backend Setup Instructions

### Step 1: Install Java (OpenJDK 17)
```sh
apt install openjdk-17-jdk -y
```

### Step 2: Install Maven
```sh
apt install maven -y
```



### Step 4: Navigate to the Backend Directory
```sh
cd flight-reservation-app/Backend/FlightReservationApp/
```

### Step 5: Set Up Database Configuration
```sh
export DATASOURCE_URL="jdbc:mysql://localhost:3306/flightdb"
export DATASOURCE_USER="DBUSER"
export DATASOURCE_PASSWORD="DBPASSWORD"
export FRONTEND_URL="http://localhost:80"
```

### Step 6: Build the Backend Application
```sh
mvn clean package
```

### Step 7: Running the Application
Once the build is successful, you can run the backend application using:
```sh
java -jar target/flight-reservation-app.jar
```

## Frontend Setup Instructions

### Step 1: Install Node.js and npm (for Frontend)
```sh
apt install nodejs npm -y
```
or
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs


### Step 2: Navigate to the Frontend Directory
```sh
cd Frontend/
```

### Step 3: Set Backend API URL
```sh
export VITE_API_URL=http://<BACKEND-IP>:8080
```
or vim /etc/profile 
at end paste following
export VITE_API_URL=http://<BACKEND-IP>:8080

### Step 4: Install Frontend Dependencies
```sh
npm install
```

### Step 5: Build the Frontend Application
```sh
npm run build
```

### Step 6: Install and Start Apache Web Server
```sh
apt install apache2 -y
systemctl start apache2
```

### Step 7: Deploy Frontend to Apache Server
```sh
cp -rf dist/* /var/www/html/
```


## Have fun with your application
```sh
URL: http://<IP>:80
user: admin
pass: admin123
```
