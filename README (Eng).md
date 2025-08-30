# 📦 ShortageRegister — Web application for product acceptance

Welcome!
This project is designed to organize the process of receiving goods in grocery stores and supermarkets.
It allows you to create and visualize **Quality Documents** recording the receipt of products from suppliers.

---

## 📄 What is a Quality Document?

A Quality Document is a digital record containing:

- Information about the delivery of goods to a specific store from a specific supplier.
- Possibility of **rejection** or **fixing defects** without rejection.
- Attaching **photos** to each product within the document.
- View all attachments and data in a single interface.

---

## ⚙️ Technical components

The project consists of the following parts:

- 🎨 **Front-End**: Vue 3 web application  
- 🧠 **Back-End**: ASP.NET Core WebAPI  
- 🗄️ **Database MSSQL**: for storing common data
- 📚 **Database PostgreSQL**: for storing Quality Documents and their parameters

---

## 🚀 Installation and launch

### 1. 📥 Downloading the project

Download the repository from GitLab to any directory on your host.

### 2. 🐳 Launch via Docker

Run the command:

  ```bash
    docker compose up --build
  ```
After launching, Docker Desktop will have 4 containers, grouped into the ShortageRegister section.

### 3. 🗄️ Initializing databases
  ### 3.1. PostgreSQL
   Create and fill the database :
   ```bash
     docker exec -it pqsql psql -U postgres -d ShortageRegister -f /pgsql/init.sql
   ```
  ### 3.2. MSSQL
   The MSSQL image does not have a built-in command line.
   Connect to the server via any client (for example, SSMS or Visual Studio) and run the script:
   ```bash
     docker exec -it pqsql psql -U postgres -d ShortageRegister -f /pgsql/init.sql
   ```
### 4. 🔐 Configuring HTTPS for ASP.NET Core
Generate a certificate (self-signed)
For local development:

This will generate a certificate and export it to file .

### 5.🧩 Docker Compose: HTTPS forwarding is already taken into account:

  ```bash
    environment:
      ASPNETCORE_Kestrel__Certificates__Default__Password: AR11sr11
      ASPNETCORE_Kestrel__Certificates__Default__Path: /https/aspnetapp.pfx
    volumes:
      - ${USERPROFILE}/.aspnet/https:/https:ro  

  ```
### 6. 🌐 Access the application
Open in your browser:
    http://localhost:8080
