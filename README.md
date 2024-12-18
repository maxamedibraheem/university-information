class University:
    def __init__(self, name, location):
        self.name = name
        self.location = location
        self.faculties = []

    def add_faculty(self, faculty):
        self.faculties.append(faculty)

    def list_faculties(self):
        print(f"Faculties at {self.name}:")
        for faculty in self.faculties:
            print(f"- {faculty.name}")


class Faculty:
    def __init__(self, name):
        self.name = name
        self.departments = []

    def add_department(self, department):
        self.departments.append(department)

    def list_departments(self):
        print(f"Departments in {self.name}:")
        for department in self.departments:
            print(f"- {department.name}")


class Department:
    def __init__(self, name):
        self.name = name
        self.courses = []

    def add_course(self, course):
        self.courses.append(course)

    def list_courses(self):
        print(f"Courses offered by {self.name}:")
        for course in self.courses:
            print(f"- {course.name}")


class Course:
    def __init__(self, name, code, credits):
        self.name = name
        self.code = code
        self.credits = credits

    def __str__(self):
        return f"{self.name} ({self.code}) - {self.credits} Credits"


class Student:
    def __init__(self, name, student_id):
        self.name = name
        self.student_id = student_id
        self.courses = []

    def enroll(self, course):
        self.courses.append(course)

    def list_courses(self):
        print(f"{self.name} is enrolled in:")
        for course in self.courses:
            print(f"- {course}")


# Example usage
if __name__ == "__main__":
    # Create a university
    my_university = University("Global Tech University", "New York")

    # Create faculties
    science_faculty = Faculty("Faculty of Science")
    arts_faculty = Faculty("Faculty of Arts")

    # Add faculties to the university
    my_university.add_faculty(science_faculty)
    my_university.add_faculty(arts_faculty)

    # Create departments
    cs_department = Department("Department of Computer Science")
    physics_department = Department("Department of Physics")

    # Add departments to the faculty
    science_faculty.add_department(cs_department)
    science_faculty.add_department(physics_department)

    # Create courses
    course1 = Course("Introduction to Programming", "CS101", 3)
    course2 = Course("Data Structures", "CS102", 4)
    course3 = Course("Quantum Mechanics", "PHY201", 3)

    # Add courses to departments
    cs_department.add_course(course1)
    cs_department.add_course(course2)
    physics_department.add_course(course3)

    # Create a student
    student1 = Student("Alice Johnson", "S12345")

    # Enroll the student in courses
    student1.enroll(course1)
    student1.enroll(course3)

    # Display university structure
    my_university.list_faculties()
    science_faculty.list_departments()
    cs_department.list_courses()

    # Display student enrollment
    student1.list_courses()
