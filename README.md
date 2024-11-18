# Inventory-API
A backend service for managing and tracking inventory in real time. Features include real-time stock updates, product management, low stock alerts, and reporting on inventory movements. Supports multiple warehouses and integrates with secure authentication methods for efficient access.

# Features  
- Real-Time Inventory Tracking: Monitor stock levels and updates across multiple locations.  
- Product Management: Add, update, and remove products with detailed information.  
- Low Stock Alerts: Notifications when inventory is low or needs to be reordered.  
- Reporting: Generate reports on stock levels, product movements, and trends.  
- Multi-Warehouse Support: Manage inventory across multiple warehouses or stores.

# Technologies Used  
- Backend Framework: Spring Boot  
- Database: Oracle Database (Oracle XE)  
- JDBC Driver: Oracle JDBC Driver ('ojdbc8.jar')  
- Authentication: JWT for secure access  
- API Documentation: Swagger/OpenAPI  
- Caching: Redis (optional)  

# Set Up the Environment  
1. Install Oracle XE (Oracle Database Express Edition):  
   - Download from [Oracle XE Downloads](https://www.oracle.com/database/technologies/xe-downloads.html).  

2. Configure Database:  
   - Create the necessary database schema and tables for the inventory system.  
   - Example connection URL:  
     '''env
     DATABASE_URL=jdbc:oracle:thin:@localhost:1521:xe
     '''

3. Set up the environment variables:  
   - Create a '.env' file or set system environment variables for the Oracle database connection:  
     '''env
     DATABASE_URL=jdbc:oracle:thin:@localhost:1521:xe
     DB_USERNAME=your_username
     DB_PASSWORD=your_password
     REDIS_URL=redis://localhost:6379  # optional
     JWT_SECRET_KEY=your_jwt_secret_key
     '''

4. Add Oracle JDBC Driver:  
   - Ensure you have the Oracle JDBC Driver ('ojdbc8.jar') in your classpath or add it as a dependency in 'pom.xml' if you're using Maven:  
     '''xml
     <dependency>
         <groupId>com.oracle.database.jdbc</groupId>
         <artifactId>ojdbc8</artifactId>
         <version>19.8.0.0</version>
     </dependency>
     '''

5. Run the Application:  
   - To start the Spring Boot application:  
     '''bash
     mvn spring-boot:run
     '''

# Usage  
- Start the API server using Spring Boot:  
  '''bash
  mvn spring-boot:run
  '''  
- Access the API documentation at:  
  '''
  http://localhost:8080/swagger-ui.html
  '''

# Endpoints  
| Endpoint                     | Method | Description                            |  
|------------------------------|--------|----------------------------------------|  
| '/inventory/add'             | POST   | Add a new product to the inventory.    |  
| '/inventory/update/{id}'     | PUT    | Update product details by ID.          |  
| '/inventory/delete/{id}'     | DELETE | Remove a product from the inventory.   |  
| '/inventory/track/{id}'      | GET    | Get current stock level for a product. |  
| '/inventory/reports'         | GET    | Generate inventory reports.            |  

# Contributing  
Contributions are welcome! Please fork the repository and submit a pull request with detailed notes.

# License  
This project is licensed under the MIT License.

---  
For more information, contact jerry.felipe@gmail.com.
