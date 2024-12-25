# Bank-loan-System
Java Bank Loan System: A program to calculate loan amounts, interest rates, Simple interest and duration scheduled. Simple and beginner-friendly.
import java.util.Scanner;
public class Main {
    Scanner obj = new Scanner(System.in);

    int prinAmount, interest, simInterest, timePeriod, amount1,amount2,amount3;

    public void homeLoan() {
        System.out.println("\n--- Enter The Details Of Home Loan ---\n");
        System.out.print("Enter The Principal Amount: ");
        prinAmount = obj.nextInt();

        System.out.print("Enter Time Period Of Loan (in years): ");
        timePeriod = obj.nextInt();

        interest = 8; // Home loan interest rate
        simInterest = (prinAmount * timePeriod * interest) / 100;
        amount1 = simInterest + prinAmount;
    }

    public void goldLoan() {
        System.out.println("\n--- Enter The Details Of Gold Loan ---\n");
        System.out.print("Enter The Principal Amount: ");
        prinAmount = obj.nextInt();

        System.out.print("Enter Time Period Of Loan (in years): ");
        timePeriod = obj.nextInt();

        interest = 12; // Gold loan interest rate
        simInterest = (prinAmount * timePeriod * interest) / 100;
        amount2 = simInterest + prinAmount;
    }

    public void educationLoan() {
        System.out.println("\n--- Enter The Details Of Education Loan ---\n");
        System.out.print("Enter The Principal Amount: ");
        prinAmount = obj.nextInt();

        System.out.print("Enter Time Period Of Loan (in years): ");
        timePeriod = obj.nextInt();

        interest = 5; // Education loan interest rate
        simInterest = (prinAmount * timePeriod * interest) / 100;
        amount3 = simInterest + prinAmount;
    }

    public void display() {
        System.out.println("\nAmount To Be Credited In Your Account for Home loan: " + amount1);
        System.out.println("\nAmount To Be Credited In Your Account for Gold loan: " + amount2);
        System.out.println("\nAmount To Be Credited In Your Account for Education loan: " + amount3);
    }

    public static void main(String[] args) {
        Scanner obj1 = new Scanner(System.in);

        int input, choice;
        Main obj2 = new Main();

        do {
            System.out.println("\n--- LIST OF OPERATIONS ---\n");
            System.out.println("Press 1: For Home Loan");
            System.out.println("Press 2: For Gold Loan");
            System.out.println("Press 3: For Education Loan");
            System.out.println("Press 4: Display The Amount To Be Approved"
            );
            System.out.println("Press 5: EXIT");

            System.out.print("Enter Your Choice: ");
            input = obj1.nextInt();

            switch (input) {
                case 1:
                    obj2.homeLoan();
                    break;
                case 2:
                    obj2.goldLoan();
                    break;
                case 3:
                    obj2.educationLoan();
                    break;
                case 4:
                    obj2.display();
                    break;
                case 5:
                    System.out.println("\nExiting The Application. Thank You!");
                    return; // Exit the program
                default:
                    System.out.println("\nINVALID INPUT. Please Try Again.");
            }

            System.out.print("\nDo You Want To Perform Another Operation? (1 for Yes / 0 for No): ");
            choice = obj1.nextInt();
        } while (choice == 1);

        obj1.close(); // Close the scanner to release resources
    }
}
