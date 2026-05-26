# Python-program-
01
# Student Management CLI Tool
students = []
# Function to add student
def add_student():
name = input("Enter student name: ")
age = int(input("Enter age: "))
subjects = input("Enter subjects (comma separated): ").split(',')
marks = []
for subject in subjects:
mark = float(input(f"Enter marks for {subject.strip()}: "))
marks.append(mark)
student = {
"name": name,
"age": age,
"subjects": [s.strip() for s in subjects],
"marks": marks
}
students.append(student)
print("\nStudent added successfully!\n")
# Function to display all students
def view_students():
if not students:
print("\nNo student records found.\n")
return
print("\n----- Student Records -----")
for i, student in enumerate(students, start=1):
print(f"\nStudent {i}")
print(f"Name : {student['name']}")
print(f"Age : {student['age']}")
print(f"Subjects : {', '.join(student['subjects'])}")
print(f"Marks : {student['marks']}")
print(f"Average : {sum(student['marks']) / len(student['marks']):.2f}")
# Function to search student
def search_student():
search_name = input("Enter student name to search: ")
found = False
for student in students:
if student['name'].lower() == search_name.lower():
found = True
print("\nStudent Found!")
print(f"Name : {student['name']}")
print(f"Age : {student['age']}")
print(f"Subjects : {', '.join(student['subjects'])}")
print(f"Marks : {student['marks']}")
print(f"Average : {sum(student['marks']) / len(student['marks']):.2f}")
if not found:
print("\nStudent not found.")
# Function to delete student
def delete_student():
name = input("Enter student name to delete: ")
for student in students:
if student['name'].lower() == name.lower():
students.remove(student)
print("\nStudent deleted successfully!")
return
print("\nStudent not found.")
# Main CLI Menu
while True:
print("\n====== Student Management System ======")
print("1. Add Student")
print("2. View Students")
print("3. Search Student")
print("4. Delete Student")
print("5. Exit")
choice = input("Enter your choice: ")
if choice == '1':
add_student()
elif choice == '2':
view_students()
elif choice == '3':
search_student()
elif choice == '4':
delete_student()
elif choice == '5':
print("\nExiting program...")
break
else:
print("\nInvalid choice! Please try again.")
