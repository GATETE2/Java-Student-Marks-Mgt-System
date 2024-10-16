```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Project {
    public static double percentage = 0.0;
    public static double total = 0.0;
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("Project");
        frame.setSize(500, 400);
        frame.setLocationRelativeTo(null);
        frame.setResizable(false);
        frame.setLayout(null);

        JButton bHome = new JButton("HOME");
        bHome.setBounds(10, 10, 100, 30);
        bHome.setFont(new Font("Arial", Font.BOLD, 15));
        bHome.setBackground(new Color(135, 206, 235)); // Light Blue
        bHome.setForeground(Color.BLACK); // Black text
        frame.add(bHome);

        JButton bStudent = new JButton("STUDENT");
        bStudent.setBounds(130, 10, 110, 30);
        bStudent.setFont(new Font("Arial", Font.BOLD, 15));
        bStudent.setBackground(new Color(144, 238, 144)); // Light Green
        bStudent.setForeground(Color.BLACK);
        frame.add(bStudent);

        JButton bLecture = new JButton("Lectures");
        bLecture.setBounds(250, 10, 120, 30);
        bLecture.setFont(new Font("Arial", Font.BOLD, 15));
        bLecture.setBackground(new Color(255, 165, 0)); // Orange
        bLecture.setForeground(Color.BLACK);
        frame.add(bLecture);

        JButton bHelp = new JButton("HELP");
        bHelp.setBounds(380, 10, 90, 30);
        bHelp.setFont(new Font("Arial", Font.BOLD, 15));
        bHelp.setBackground(new Color(255, 69, 0)); // Red-Orange
        bHelp.setForeground(Color.WHITE); // White text
        frame.add(bHelp);

        JLabel lb1 = new JLabel("Chemistry /40:");
        lb1.setBounds(10, 50, 125, 30);
        lb1.setFont(new Font("Arial", Font.BOLD, 15));
        frame.add(lb1);

        JTextField tf1 = new JTextField();
        tf1.setBounds(150, 50, 150, 30);
        frame.add(tf1);

        JLabel lb2 = new JLabel("    Biology /40:");
        lb2.setBounds(10, 90, 125, 30);
        lb2.setFont(new Font("Arial", Font.BOLD, 15));
        lb2.setAlignmentX(Component.LEFT_ALIGNMENT);
        frame.add(lb2);

        JTextField tf2 = new JTextField();
        tf2.setBounds(150, 90, 150, 30);
        frame.add(tf2);

        JLabel lb3 = new JLabel("     Physics /40:");
        lb3.setBounds(10, 130, 125, 30);
        lb3.setFont(new Font("Arial", Font.BOLD, 15));
        lb3.setAlignmentX(Component.LEFT_ALIGNMENT);
        frame.add(lb3);

        JTextField tf3 = new JTextField();
        tf3.setBounds(150, 130, 150, 30);
        frame.add(tf3);

        JLabel lb4 = new JLabel("           Math /40:");
        lb4.setBounds(10, 170, 125, 30);
        lb4.setFont(new Font("Arial", Font.BOLD, 15));
        lb4.setAlignmentX(Component.LEFT_ALIGNMENT);
        frame.add(lb4);

        JTextField tf4 = new JTextField();
        tf4.setBounds(150, 170, 150, 30);
        frame.add(tf4);

        JButton bAll = new JButton("DISPLAY ALL THE ANSWERS DOWN HERE");
        bAll.setFont(new Font("Arial", Font.BOLD, 15));
        bAll.setBounds(10, 220, 460, 30);
        bAll.setBackground(new Color(173, 216, 230)); // Light Blue
        bAll.setForeground(Color.BLACK);
        frame.add(bAll);

        JButton bPercent = new JButton("PERCENTAGE");
        bPercent.setFont(new Font("Arial", Font.BOLD, 15));
        bPercent.setBounds(10, 270, 150, 30);
        bPercent.setBackground(new Color(173, 216, 230));
        bPercent.setForeground(Color.BLACK);
        frame.add(bPercent);

        JTextField tf5 = new JTextField();
        tf5.setBounds(10, 310, 150, 30);
        frame.add(tf5);

        JButton bAverage = new JButton("AVERAGE");
        bAverage.setFont(new Font("Arial", Font.BOLD, 15));
        bAverage.setBounds(180, 270, 150, 30);
        bAverage.setBackground(new Color(173, 216, 230));
        bAverage.setForeground(Color.BLACK);
        frame.add(bAverage);

        JTextField tf6 = new JTextField();
        tf6.setBounds(180, 310, 150, 30);
        frame.add(tf6);

        JButton bGrade = new JButton("GRADE");
        bGrade.setFont(new Font("Arial", Font.BOLD, 15));
        bGrade.setBounds(350, 270, 120, 30);
        bGrade.setBackground(new Color(173, 216, 230));
        bGrade.setForeground(Color.BLACK);
        frame.add(bGrade);

        JTextField tf7 = new JTextField();
        tf7.setBounds(350, 310, 120, 30);
        frame.add(tf7);

        bPercent.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String s1 = tf1.getText();
                String s2 = tf2.getText();
                String s3 = tf3.getText();
                String s4 = tf4.getText();
                double n1 = Integer.parseInt(s1);
                double n2 = Integer.parseInt(s2);
                double n3 = Integer.parseInt(s3);
                double n4 = Integer.parseInt(s4);
                double percentage = ((n1 + n2 + n3 + n4) / 160) * 100;

                if (percentage <= 100 && percentage >= 0) {
                    tf5.setText("     " + String.format("%.2f", percentage) + "%");
                } else {
                    tf5.setText("   Invalid percentage");
                }
            }
        });

        bAverage.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String s1 = tf1.getText();
                String s2 = tf2.getText();
                String s3 = tf3.getText();
                String s4 = tf4.getText();
                double n1 = Integer.parseInt(s1);
                double n2 = Integer.parseInt(s2);
                double n3 = Integer.parseInt(s3);
                double n4 = Integer.parseInt(s4);
                double average = (n1 + n2 + n3 + n4) / 4;

                tf6.setText("      " + String.format("%.2f", average));
            }
        });

        bGrade.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String s1 = tf1.getText();
                String s2 = tf2.getText();
                String s3 = tf3.getText();
                String s4 = tf4.getText();
                double n1 = Integer.parseInt(s1);
                double n2 = Integer.parseInt(s2);
                double n3 = Integer.parseInt(s3);
                double n4 = Integer.parseInt(s4);
                double p = ((n1 + n2 + n3 + n4) / 160) * 100;

                if (p <= 100 && p >= 80) {
                    tf7.setText("  Grade A");
                } else if (p <= 79 && p >= 70) {
                    tf7.setText("  Grade B");
                } else if (p <= 69 && p >= 60) {
                    tf7.setText("  Grade C");
                } else if (p <= 59 && p >= 50) {
                    tf7.setText("  Grade D");
                } else if (p < 50) {
                    tf7.setText("  Failed");
                } else {
                    tf7.setText("  Invalid");
                }
            }
        });

        bAll.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                bPercent.doClick();
                bAverage.doClick();
                bGrade.doClick();
            }
        });
        frame.setVisible(true);
    }
}
