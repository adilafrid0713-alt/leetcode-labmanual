import java.util.*;
import java.util.stream.Collectors;

class Employee {
    private String name;
    private String department;
    private double salary;

    public Employee(String name, String department, double salary) {
        this.name = name;
        this.department = department;
        this.salary = salary;
    }

    public String getName() { return name; }
    public String getDepartment() { return department; }
    public double getSalary() { return salary; }

    @Override
    public String toString() {
        return String.format("%s (%s) - $%.2f", name, department, salary);
    }
}

public class EmployeeAnalytics {
    public static void main(String[] args) {
        List<Employee> employees = Arrays.asList(
            new Employee("Alice", "IT", 75000),
            new Employee("Bob", "HR", 55000),
            new Employee("Charlie", "IT", 85000),
            new Employee("David", "Finance", 90000),
            new Employee("Eve", "HR", 60000)
        );

        System.out.println("--- Employee Data Analytics ---");

        // 1. Filter: Employees in IT
        System.out.println("\n1. IT Department Employees:");
        employees.stream()
                .filter(e -> e.getDepartment().equals("IT"))
                .forEach(System.out::println);

        // 2. Sort: By Salary (Descending)
        System.out.println("\n2. Employees sorted by Salary (Highest to Lowest):");
        employees.stream()
                .sorted(Comparator.comparingDouble(Employee::getSalary).reversed())
                .forEach(System.out::println);

        // 3. Group: By Department
        System.out.println("\n3. Employees grouped by Department:");
        Map<String, List<Employee>> byDept = employees.stream()
                .collect(Collectors.groupingBy(Employee::getDepartment));
        byDept.forEach((dept, list) -> {
            System.out.println(dept + ": " + list.stream().map(Employee::getName).collect(Collectors.joining(", ")));
        });

        // 4. Summarize: Average Salary
        System.out.println("\n4. Summary Analytics:");
        double avgSalary = employees.stream()
                .mapToDouble(Employee::getSalary)
                .average()
                .orElse(0.0);
        System.out.printf("Average Company Salary: $%.2f\n", avgSalary);
    }
}
