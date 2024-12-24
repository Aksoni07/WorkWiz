# ** WorkWiz : An Employee Management System**  
_A comprehensive database solution designed using MySQL and PL/SQL for managing biographical and organizational information of employees._

---

## **Overview**  
The Employee Management System is a robust database design aimed at storing and managing employee information, including their biographical data, organizational details, performance records, and salary computations. This system provides:  
- An **Entity-Relationship Model (ER Model)** to represent the structure of data.
- Translation of the ER model into a **Relational Schema** for implementation.  
- **Stored Procedures** for efficient data manipulation.  
- **Views** for streamlined data retrieval.  

---

## **Key Features**  
1. **Entity-Relationship Model**  
   - A clear representation of the relationships between different entities, such as Employees, Roles, Organizations, and Addresses.

2. **Relational Schema**  
   - Translated the ER model into a well-structured schema to ensure efficient data storage and normalization.

3. **Data Insertion Examples**  
   - Sample `INSERT` statements for quick setup and testing of data in tables like `Employee`, `Employee_Role`, `Address_Type`, `Employee_Type`, etc.

4. **Stored Procedures**  
   - Simplifies repetitive tasks like data insertion and updates, enhancing consistency and reducing manual errors.

5. **Views**  
   - Predefined SQL queries that make data retrieval faster and simpler, providing users with meaningful insights.

---

## **Database Schema**  
### **Tables Created**:  
1. **Address_Type**  
   Stores different types of addresses with descriptions.  
   - _Example_:  
   ```sql
   INSERT INTO address_type (address_id, address_type, address_type_description)
   VALUES (1, 'Home', 'Decentralized static approach');
   ```

2. **Employee_Type**  
   Defines employee classifications and their respective pay types and compensation details.  
   - _Example_:  
   ```sql
   INSERT INTO Employee_Type (employee_type_id, employee_type, employee_type_desc, pay_type, compensation_package)
   VALUES (1, 'Training', 'Configurable attitude-oriented leverage', 'Bi-Weekly', 0.03);
   ```

3. **Employee_Role**  
   Specifies various roles within the organization along with their descriptions.  
   - _Example_:  
   ```sql
   INSERT INTO Employee_Role (employee_role_id, role_name, role_desc)
   VALUES (1, 'Product Manager', 'Decentralized systemic productivity');
   ```

4. **Organization**  
   Maintains organizational details like client name, code, and domain.  
   - _Example_:  
   ```sql
   INSERT INTO Organization (organization_id, client_org_name, client_org_code, client_org_domain, availability_date)
   VALUES (1, 'Boeing', 3, 'Manufacturing', '2020-07-12');
   ```

5. **Employee**  
   Contains biographical and organizational details of employees.  
   - _Example_:  
   ```sql
   INSERT INTO employee (employee_id, employee_role_id, employee_type_id, organization_id, home_country, work_country, gender)
   VALUES (1, 28, 33, 8, 'Costa Rica', 'Denmark', 'F');
   ```

6. **Person**  
   Stores personal details like names, contact information, and age.  
   - _Example_:  
   ```sql
   INSERT INTO Person (person_id, first_name, middle_name, last_name, age, phone_number, email_id)
   VALUES (1, 'Bessy', 'Stillman', 'Maxfield', 53, '110 205 3647', 'smaxfield0@sohu.com');
   ```

---

## **Setup Instructions**  
1. Clone this repository to your local machine:  
   ```bash
   git clone https://github.com/<YourGitHubHandle>/EmployeeManagementSystem.git
   ```

2. Navigate to the project directory:  
   ```bash
   cd EmployeeManagementSystem
   ```

3. Import the `Project.sql` file into your MySQL environment to set up the database:  
   ```sql
   SOURCE /path/to/Project.sql;
   ```

4. Test the database using the included `INSERT` statements to ensure everything is working as expected.

---

## **How It Works**  
- **Data Insertion**: Populate tables with employee, organizational, and address details using pre-written `INSERT` queries.  
- **Data Retrieval**: Use pre-defined **Views** or write custom queries to fetch information about employees, roles, and organizations.  
- **Automation**: Utilize **Stored Procedures** for bulk insertion or updates.  

---

## **Examples**  
- Retrieve all employees working in a specific organization:  
   ```sql
   SELECT e.employee_id, p.first_name, p.last_name, o.client_org_name
   FROM employee e
   JOIN person p ON e.person_id = p.person_id
   JOIN organization o ON e.organization_id = o.organization_id
   WHERE o.client_org_name = 'Boeing';
   ```

- Add a new employee to the system:  
   ```sql
   CALL AddNewEmployee('John', 'Doe', 'Smith', 30, '1234567890', 'johndoe@example.com', 'USA', 'Canada', 'M', 'Single');
   ```

---

## **Contributing**  
Contributions are welcome! If you'd like to contribute, please fork this repository, make your changes, and submit a pull request.  
