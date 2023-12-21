# ExpenceTracker
import java.util.ArrayList;
import java.util.Scanner;

class Expense {
    String category;
    double amount;

    public Expense(String category, double amount) {
        this.category = category;
        this.amount = amount;
    }
}

public class ExpenseTracker {
    public static void main(String[] args) {
        ArrayList<Expense> expenses = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("1. Add Expense");
            System.out.println("2. View Expenses");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");

            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    addExpense(expenses);
                    break;
                case 2:
                    viewExpenses(expenses);
                    break;
                case 3:
                    System.out.println("Exiting Expense Tracker. Goodbye!");
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void addExpense(ArrayList<Expense> expenses) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter expense category: ");
        String category = scanner.next();

        System.out.print("Enter expense amount: ");
        double amount = scanner.nextDouble();

        Expense expense = new Expense(category, amount);
        expenses.add(expense);

        System.out.println("Expense added successfully!");
    }

    private static void viewExpenses(ArrayList<Expense> expenses) {
        if (expenses.isEmpty()) {
            System.out.println("No expenses to display.");
        } else {
            System.out.println("Expense List:");
            for (Expense expense : expenses) {
                System.out.println("Category: " + expense.category + ", Amount: $" + expense.amount);
            }
        }
    }
}
