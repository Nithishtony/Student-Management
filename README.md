# Student Management System
Nithish Tony na Flower illa da Fire uh💥💥

def show_menu():
    print("\nStudent Management System")
    print("1. Add Student")
    print("2. View All Students")
    print("3. Search Student by ID")
    print("4. Delete Student by ID")
    print("5. Exit")

def add_student(student_list):
    student_id = input("Enter Student ID: ")
    name = input("Enter Student Name: ")
    age = input("Enter Student Age: ")
    course = input("Enter Student Course: ")
    
    student = {
        "ID": student_id,
        "Name": name,
        "Age": age,
        "Course": course
    }
    student_list.append(student)
    print("Student added successfully!")

def view_students(student_list):
    if not student_list:
        print("No students found.")
        return

    print("\nAll Students:")
    for student in student_list:
        print(f"ID: {student['ID']}, Name: {student['Name']}, Age: {student['Age']}, Course: {student['Course']}")

def search_student(student_list):
    student_id = input("Enter Student ID to search: ")
    for student in student_list:
        if student['ID'] == student_id:
            print(f"Student found: ID: {student['ID']}, Name: {student['Name']}, Age: {student['Age']}, Course: {student['Course']}")
            return
    print("Student not found.")

def delete_student(student_list):
    student_id = input("Enter Student ID to delete: ")
    for student in student_list:
        if student['ID'] == student_id:
            student_list.remove(student)
            print("Student deleted successfully!")
            return
    print("Student not found.")

def main():
    student_list = []
    while True:
        show_menu()
        choice = input("Enter your choice (1-5): ")

        if choice == '1':
            add_student(student_list)
        elif choice == '2':
            view_students(student_list)
        elif choice == '3':
            search_student(student_list)
        elif choice == '4':
            delete_student(student_list)
        elif choice == '5':
            print("Exiting the program. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
