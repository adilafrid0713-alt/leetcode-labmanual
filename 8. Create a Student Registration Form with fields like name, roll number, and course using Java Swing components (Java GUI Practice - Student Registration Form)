import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class StudentRegistrationForm extends JFrame {
    private JTextField txtName, txtRollNo, txtCourse;
    private JButton btnSubmit;

    public StudentRegistrationForm() {
        setTitle("Student Registration Form");
        setSize(350, 250);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(4, 2, 10, 10));

        // Labels
        JLabel lblName = new JLabel(" Student Name:");
        JLabel lblRollNo = new JLabel(" Roll Number:");
        JLabel lblCourse = new JLabel(" Course:");

        // Text Fields
        txtName = new JTextField();
        txtRollNo = new JTextField();
        txtCourse = new JTextField();

        // Button
        btnSubmit = new JButton("Register");

        // Add components
        add(lblName); add(txtName);
        add(lblRollNo); add(txtRollNo);
        add(lblCourse); add(txtCourse);
        add(new JLabel("")); // Empty cell for alignment
        add(btnSubmit);

        // Action Listener
        btnSubmit.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String name = txtName.getText();
                String rollNo = txtRollNo.getText();
                String course = txtCourse.getText();

                if(name.isEmpty() || rollNo.isEmpty() || course.isEmpty()) {
                    JOptionPane.showMessageDialog(null, "Please fill all fields!", "Error", JOptionPane.ERROR_MESSAGE);
                } else {
                    JOptionPane.showMessageDialog(null, 
                        "Registration Successful!\nName: " + name + "\nRoll: " + rollNo + "\nCourse: " + course, 
                        "Success", JOptionPane.INFORMATION_MESSAGE);
                }
            }
        });
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            new StudentRegistrationForm().setVisible(true);
        });
    }
}
