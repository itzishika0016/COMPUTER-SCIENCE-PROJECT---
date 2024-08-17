import sqlite3

# Create a connection to the database
conn = sqlite3.connect('employee.db')
c = conn.cursor()

# Create a table to store employee information
c.execute('''CREATE TABLE IF NOT EXISTS employees (
             id INTEGER PRIMARY KEY,
             name TEXT NOT NULL,
             age INTEGER,
             position TEXT,
             salary REAL
             )''')

# Function to add a new employee to the database
def add_employee(name, age, position, salary):
    c.execute("INSERT INTO employees (name, age, position, salary) VALUES (?, ?, ?, ?)", (name, age, position, salary))
    conn.commit()
    print("Employee added successfully")

# Function to view all employees in the database
def view_employees():
    c.execute("SELECT * FROM employees")
    rows = c.fetchall()
    for row in rows:
        print(row)

# Function to update an employee's information
def update_employee(id, name, age, position, salary):
    c.execute("UPDATE employees SET name=?, age=?, position=?, salary=? WHERE id=?", (name, age, position, salary, id))
    conn.commit()
    print("Employee updated successfully")

# Function to delete an employee from the database
def delete_employee(id):
    c.execute("DELETE FROM employees WHERE id=?", (id,))
    conn.commit()
    print("Employee deleted successfully")

# Main program loop
while True:
    print("\nEmployee Management System")
    print("1. Add Employee")
    print("2. View Employees")
    print("3. Update Employee")
    print("4. Delete Employee")
    print("5. Exit")

    choice = input("\nEnter your choice: ")

    if choice == '1':
        name = input("Enter employee name: ")
        age = int(input("Enter employee age: "))
        position = input("Enter employee position: ")
        salary = float(input("Enter employee salary: "))
        add_employee(name, age, position, salary)
    
    elif choice == '2':
        view_employees()

    
     elif choice == '3':
         id = int(input("Enter employee ID to update: "))
         name = input("Enter new name: ")
         age = int(input("Enter new age: "))
         position = input("Enter new position: ")
         salary = float(input("Enter new salary: "))
         update_employee(id,name ,age ,position ,salary )
    
     elif choice == '4':
          id= int(input ("enter the ID of the employe you want to delete"))
          delete_employee(id)
    
     elif choice == '5':
          break
    
     else:
          print ("Invalid Choice")

# Close the connection to the database when done
conn.close(
