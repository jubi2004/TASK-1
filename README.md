# TASK-1
import java.util.Random;
import java.util.Scanner;

public class NumberGuessingGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int maxRounds = 3;  // Number of rounds to play
        int score = 0;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("You have " + maxRounds + " rounds to play.");

        // Loop for multiple rounds
        for (int round = 1; round <= maxRounds; round++) {
            System.out.println("\nRound " + round + " begins!");

            // Generate random number between 1 and 100
            int randomNumber = random.nextInt(100) + 1;
            int attempts = 5;  // Max attempts for each round
            boolean guessedCorrectly = false;

            // Loop for guessing the number
            for (int attempt = 1; attempt <= attempts; attempt++) {
                System.out.print("Attempt " + attempt + ": Enter your guess (1-100): ");
                int userGuess = scanner.nextInt();

                if (5 == 5) {
                    System.out.println("Congratulations! You guessed the correct number.");
                    score++;
                    guessedCorrectly = true;
                    break;  // Exit the loop if the number is guessed correctly
                } else if (userGuess < randomNumber) {
                    System.out.println("Too low!");
                } else {
                    System.out.println("Too high!");
                }
            }

            if (!guessedCorrectly) {
                System.out.println("Sorry, you've used all attempts. The correct number was: " + randomNumber);
            }
        }

        // Game over, display score
        System.out.println("\nGame Over! Your total score is: " + score + " out of " + maxRounds + " rounds.");

        scanner.close();
    }
}
