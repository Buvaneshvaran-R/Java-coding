package assignment_1;

// Base class
class Course {
    String courseName;
    int duration; // in weeks

    Course(String courseName, int duration) {
        this.courseName = courseName;
        this.duration = duration;
    }

    void displayDetails() {
        System.out.println("Course: " + courseName + ", Duration: " + duration + " weeks");
    }
}

// Derived classes
class OnlineCourse extends Course {
    String platform;

    OnlineCourse(String name, int duration, String platform) {
        super(name, duration);
        this.platform = platform;
    }

    @Override
    void displayDetails() {
        super.displayDetails();
        System.out.println("Platform: " + platform);
    }
}

class OfflineCourse extends Course {
    String location;

    OfflineCourse(String name, int duration, String location) {
        super(name, duration);
        this.location = location;
    }

    @Override
    void displayDetails() {
        super.displayDetails();
        System.out.println("Location: " + location);
    }
}

// User Roles
class User {
    String name;

    User(String name) {
        this.name = name;
    }

    void role() {
        System.out.println(name + " is a general user.");
    }
}

class Student extends User {
    Student(String name) {
        super(name);
    }

    @Override
    void role() {
        System.out.println(name + " is a Student.");
    }
}

class Instructor extends User {
    Instructor(String name) {
        super(name);
    }

    @Override
    void role() {
        System.out.println(name + " is an Instructor.");
    }
}

// Main class
public class ASIGN {
    public static void main(String[] args) {
        Course c1 = new OnlineCourse("Java Programming", 6, "Coursera");
        Course c2 = new OfflineCourse("Data Structures", 8, "Campus Hall A");

        User u1 = new Student("Alice");
        User u2 = new Instructor("Dr. Bob");

        c1.displayDetails();
        c2.displayDetails();
        u1.role();
        u2.role();
    }
}
