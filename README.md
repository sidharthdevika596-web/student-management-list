#internship 

# student-management-list

students = []


def add_student():
    student_id = input("Enter Student ID: ")
    name = input("Enter Student Name: ")
    age = input("Enter Student Age: ")

    student = {
        "id": student_id,
        "name": name,
        "age": age
    }

    students.append(student)
    print("Student added successfully!\n")


def view_students():
    if len(students) == 0:
        print("No students found.\n")
        return

    print("\nStudent List:")
    for student in students:
        print(f"ID: {student['id']}, Name: {student['name']}, Age: {student['age']}")
    print()


def delete_student():
    student_id = input("Enter Student ID to delete: ")

    for student in students:
        if student["id"] == student_id:
            students.remove(student)
            print("Student deleted successfully!\n")
            return

    print("Student not found.\n")


def menu():
    while True:
        print("===== Student Management System =====")
        print("1. Add Student")
        print("2. View Students")
        print("3. Delete Student")
        print("4. Exit")

        choice = input("Enter choice: ")

        if choice == "1":
            add_student()
        elif choice == "2":
            view_students()
        elif choice == "3":
            delete_student()
        elif choice == "4":
            print("Exiting...")
            break
        else:
            print("Invalid choice.\n")


menu()