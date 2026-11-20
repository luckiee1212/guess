import java.util.Scanner;
import java.util.Random;

public class GuessingGame {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Random random = new Random();

        String playAgain = "yes";

        while (playAgain.equalsIgnoreCase("yes")) {

            int number = random.nextInt(100) + 1;
            int guess = 0;
            int attempts = 0;

            System.out.println("Welcome to Guessing Number Game!");
            System.out.println("Guess a number between 1 and 100");

            while (guess != number) {

                System.out.print("Enter your guess: ");
                guess = sc.nextInt();

                attempts++;

                if (guess > number) {

                    System.out.println("Too High! Try Again.");

                } else if (guess < number) {

                    System.out.println("Too Low! Try Again.");

                } else {

                    System.out.println("Congratulations! You Win!");
                    System.out.println("Total Attempts: " + attempts);

                }
            }

            System.out.print("Play Again? (yes/no): ");
            playAgain = sc.next();

        }

        System.out.println("Thank you for playing!");

        sc.close();
    }
}
