import java.sql.*;
import java.util.Scanner;

public class StudentDatabaseJDBC {
    // Update these according to your database setup
    static final String DB_URL = "jdbc:mysql://localhost:3306/lab_db";
    static final String USER = "root";
    static final String PASS = "password";

    public static void main(String[] args) {
        try (Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
             Scanner scanner = new Scanner(System.in)) {
             
            System.out.println("Connected to Database!");

            while (true) {
                System.out.println("\n1. Add Student\n2. View Students\n3. Update Student\n4. Delete Student\n5. Exit");
                System.out.print("Choose an option: ");
                int choice = scanner.nextInt();

                if (choice == 1) {
                    System.out.print("Enter ID: "); int id = scanner.nextInt();
                    System.out.print("Enter Name: "); String name = scanner.next();
                    System.out.print("Enter Course: "); String course = scanner.next();
                    
                    String sql = "INSERT INTO students (id, name, course) VALUES (?, ?, ?)";
                    PreparedStatement pstmt = conn.prepareStatement(sql);
                    pstmt.setInt(1, id); pstmt.setString(2, name); pstmt.setString(3, course);
                    pstmt.executeUpdate();
                    System.out.println("Student Added!");
                } 
                else if (choice == 2) {
                    Statement stmt = conn.createStatement();
                    ResultSet rs = stmt.executeQuery("SELECT * FROM students");
                    System.out.println("\n--- Student Records ---");
                    while (rs.next()) {
                        System.out.println("ID: " + rs.getInt("id") + ", Name: " + rs.getString("name") + ", Course: " + rs.getString("course"));
                    }
                } 
                else if (choice == 3) {
                    System.out.print("Enter Student ID to update: "); int id = scanner.nextInt();
                    System.out.print("Enter New Course: "); String course = scanner.next();
                    
                    String sql = "UPDATE students SET course = ? WHERE id = ?";
                    PreparedStatement pstmt = conn.prepareStatement(sql);
                    pstmt.setString(1, course); pstmt.setInt(2, id);
                    pstmt.executeUpdate();
                    System.out.println("Student Updated!");
                } 
                else if (choice == 4) {
                    System.out.print("Enter Student ID to delete: "); int id = scanner.nextInt();
                    String sql = "DELETE FROM students WHERE id = ?";
                    PreparedStatement pstmt = conn.prepareStatement(sql);
                    pstmt.setInt(1, id);
                    pstmt.executeUpdate();
                    System.out.println("Student Deleted!");
                } 
                else if (choice == 5) {
                    break;
                }
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
