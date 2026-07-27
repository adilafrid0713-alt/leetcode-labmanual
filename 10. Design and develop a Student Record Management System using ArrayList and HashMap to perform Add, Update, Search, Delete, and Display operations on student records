import java.util.*;

class StudentRecord {
    int rollNo;
    String name;
    String course;

    public StudentRecord(int rollNo, String name, String course) {
        this.rollNo = rollNo;
        this.name = name;
        this.course = course;
    }

    @Override
    public String toString() {
        return "Roll No: " + rollNo + " | Name: " + name + " | Course: " + course;
    }
}

public class StudentManagerCollections {
    // HashMap for fast O(1) Search, Update, and Delete based on Roll No
    private Map<Integer, StudentRecord> studentMap = new HashMap<>();
    // ArrayList to maintain a sequential list if iteration/ordering is needed
    private List<StudentRecord> studentList = new ArrayList<>();

    public void addStudent(int rollNo, String name, String course) {
        if (studentMap.containsKey(rollNo)) {
            System.out.println("Error: Student with this Roll Number already exists.");
            return;
        }
        StudentRecord s = new StudentRecord(rollNo, name, course);
        studentMap.put(rollNo, s);
        studentList.add(s);
        System.out.println("Student Added Successfully!");
    }

    public void updateStudent(int rollNo, String newName, String newCourse) {
        if (studentMap.containsKey(rollNo)) {
            StudentRecord s = studentMap.get(rollNo);
            s.name = newName;
            s.course = newCourse;
            System.out.println("Student Updated Successfully!");
        } else {
            System.out.println("Student not found!");
        }
    }

    public void searchStudent(int rollNo) {
        if (studentMap.containsKey(rollNo)) {
            System.out.println("Found: " + studentMap.get(rollNo));
        } else {
            System.out.println("Student not found!");
        }
    }

    public void deleteStudent(int rollNo) {
        if (studentMap.containsKey(rollNo)) {
            StudentRecord s = studentMap.remove(rollNo);
            studentList.remove(s);
            System.out.println("Student Deleted Successfully!");
        } else {
            System.out.println("Student not found!");
        }
    }

    public void displayAll() {
        if (studentList.isEmpty()) {
            System.out.println("No records found.");
            return;
        }
        System.out.println("\n--- All Student Records ---");
        for (StudentRecord s : studentList) {
            System.out.println(s);
        }
    }

    public static void main(String[] args) {
        StudentManagerCollections manager = new StudentManagerCollections();
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("\n1. Add | 2. Update | 3. Search | 4. Delete | 5. Display All | 6. Exit");
            System.out.print("Select operation: ");
            int choice = sc.nextInt();

            if (choice == 1) {
                System.out.print("Roll No: "); int r = sc.nextInt();
                System.out.print("Name: "); String n = sc.next();
                System.out.print("Course: "); String c = sc.next();
                manager.addStudent(r, n, c);
            } else if (choice == 2) {
                System.out.print("Enter Roll No to Update: "); int r = sc.nextInt();
                System.out.print("New Name: "); String n = sc.next();
                System.out.print("New Course: "); String c = sc.next();
                manager.updateStudent(r, n, c);
            } else if (choice == 3) {
                System.out.print("Enter Roll No to Search: "); int r = sc.nextInt();
                manager.searchStudent(r);
            } else if (choice == 4) {
                System.out.print("Enter Roll No to Delete: "); int r = sc.nextInt();
                manager.deleteStudent(r);
            } else if (choice == 5) {
                manager.displayAll();
            } else if (choice == 6) {
                System.out.println("Exiting...");
                break;
            } else {
                System.out.println("Invalid choice!");
            }
        }
        sc.close();
    }
}
