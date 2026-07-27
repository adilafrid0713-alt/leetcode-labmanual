import java.util.ArrayList;
import java.util.List;

// Generic Class with a Bounded Type Parameter (only accepts Numbers)
class DataContainer<T extends Number> {
    private List<T> dataList;

    public DataContainer() {
        dataList = new ArrayList<>();
    }

    public void addData(T data) {
        dataList.add(data);
    }

    public List<T> getData() {
        return dataList;
    }

    // Generic Method to process and display items of any type safely
    public <U> void printAnyArray(U[] array) {
        for (U element : array) {
            System.out.print(element + " ");
        }
        System.out.println();
    }

    // Process data specifically for the bounded type
    public double getSum() {
        double sum = 0.0;
        for (T item : dataList) {
            sum += item.doubleValue(); // Safe because T extends Number
        }
        return sum;
    }
}

public class GenericDemo {
    public static void main(String[] args) {
        // Integer Container
        DataContainer<Integer> intContainer = new DataContainer<>();
        intContainer.addData(10);
        intContainer.addData(20);
        intContainer.addData(30);
        
        System.out.println("Integer List Sum: " + intContainer.getSum());

        // Double Container
        DataContainer<Double> doubleContainer = new DataContainer<>();
        doubleContainer.addData(10.5);
        doubleContainer.addData(20.5);
        
        System.out.println("Double List Sum: " + doubleContainer.getSum());

        // Using the Generic Method
        System.out.print("Printing String array using generic method: ");
        String[] stringArray = {"Java", "Generics", "Are", "Powerful"};
        intContainer.printAnyArray(stringArray);
    }
}
