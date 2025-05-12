import java.util.Random;
import java.util.Scanner;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

   int totalRounds = 3;
        int score = 0;
      System.out.println("Welcome to the Number Guessing Game!");
      for (int round = 1; round <= totalRounds; round++) {
            int numberToGuess = random.nextInt(100) + 1; // 1 to 100
            int attempts = 0;
            int maxAttempts = 5;
      System.out.println("\nRound " + round + ": Guess the number between 1 and 100!");
      while (attempts < maxAttempts) {
                System.out.print("Attempt " + (attempts + 1) + ": Enter your guess: ");
                int guess = scanner.nextInt();
                attempts++;
    if (guess == numberToGuess) {
                    System.out.println("Correct! You guessed the number in " + attempts + " attempts.");
                    score += (maxAttempts - attempts + 1); // More points for fewer attempts
                    break;
                } else if (guess < numberToGuess) {
                    System.out.println("Too low!");
                } else {
                    System.out.println("Too high!");
                }
                if (attempts == maxAttempts) {
                    System.out.println("Sorry! You've used all attempts. The number was: " + numberToGuess);
                }
            }
        }
        System.out.println("\nGame Over! Your total score: " + score);
        scanner.close();
    }
}
