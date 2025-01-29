import java.util.Scanner;

public class Main {

    // ATM Model class to store and manage the balance
    static class AtmModel {
        private int bankBalance = 0; // Initial balance set to 0

        // Get current balance
        public int getBankBalance() {
            return bankBalance;
        }

        // Set new balance
        public void setBankBalance(int balance) {
            this.bankBalance = balance;
        }
    }

    // Interface defining the ATM software functionality
    public interface AtmSoftware {
        void addMoney(int inputMoney);
        void withdrawMoney(int inputMoney);
        void viewBalance();
    }

    // TsBankAtm class implementing AtmSoftware interface
    static class TsBankAtm implements AtmSoftware {

        AtmModel model = new AtmModel();

        @Override
        public void addMoney(int inputMoney) {
            int balance = model.getBankBalance(); // Get current balance
            int newBalance = balance + inputMoney; // Calculate new balance
            model.setBankBalance(newBalance); // Set new balance
            System.out.println("Your new balance is: " + newBalance);
        }

        @Override
        public void withdrawMoney(int inputMoney) {
            int balance = model.getBankBalance(); // Get current balance
            int newBalance = balance - inputMoney; // Calculate new balance

            if (newBalance < 0) {
                System.out.println("Insufficient balance.");
            } else {
                model.setBankBalance(newBalance); // Set new balance
                System.out.println("Your new balance is: " + newBalance);
            }
        }

        @Override
        public void viewBalance() {
            int balance = model.getBankBalance(); // Get current balance
            System.out.println("Your balance is: " + balance);
        }
    }

    // Main method to run the ATM software
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // Use a single scanner
        TsBankAtm tsBankAtm = new TsBankAtm();
        atmSoftware(scanner, tsBankAtm); // Pass scanner and TsBankAtm instance
        scanner.close(); // Close the scanner after usage
    }

    // Method to display the ATM software menu and handle user input
    public static void atmSoftware(Scanner scanner, TsBankAtm tsBankAtm) {
        while (true) {
            System.out.println("1. Add money");
            System.out.println("2. Withdraw money");
            System.out.println("3. View balance");
            System.out.println("4. Exit");
            
            int userInput = scanner.nextInt();
            
            switch (userInput) {
                case 1:
                    System.out.println("Enter the amount to be added:");
                    int userMoney = scanner.nextInt();
                    tsBankAtm.addMoney(userMoney);
                    break;
                case 2:
                    System.out.println("Enter the amount to be withdrawn:");
                    userMoney = scanner.nextInt();
                    tsBankAtm.withdrawMoney(userMoney);
                    break;
                case 3:
                    tsBankAtm.viewBalance();
                    break;
                case 4:
                    System.out.println("Exiting... Thank you for using the ATM.");
                    return; // Exit the method
                default:
                    System.err.println("Invalid input. Please try again.");
            }
        }
    }
}
