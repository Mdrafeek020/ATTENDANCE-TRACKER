def mark_attendance(attendance_dict, employee_name):
    """Mark the attendance of an employee."""
    if employee_name in attendance_dict:
        print(f"{employee_name} is already marked present.")
    else:
        attendance_dict[employee_name] = "Present"
        print(f"{employee_name} marked present.")

def view_attendance(attendance_dict):
    """View the attendance of all employees."""
    print("Employee Attendance:")
    for employee, status in attendance_dict.items():
        print(f"{employee}: {status}")

    absent_employees = [emp for emp, status in attendance_dict.items() if status != "Present"]
    if absent_employees:
        print("Absent Employees:")
        for emp in absent_employees:
            print(emp)
    else:
        print("No employees are absent.")

def main():
    attendance = {}
    while True:
        print("\n1. Mark Attendance")
        print("2. View Attendance")
        print("3. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            employee_name = input("Enter the employee's name: ")
            mark_attendance(attendance, employee_name)
        elif choice == "2":
            view_attendance(attendance)
        elif choice == "3":
            print("Exiting program.")
            break
        else:
            print("Invalid choice. Please enter a valid option.")

if _name_ == "_main_":
    main()
