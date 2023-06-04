# Hi-Lo

import java.util.Random;
import java.util.Scanner;

public class ComputerPlayer extends HiLo{
    private final Random generator;
    private int generatedNumber;
    private int numberOfAttempts;
    Scanner scan;
    
    public ComputerPlayer()
    {
        generator = new Random();
        scan = new Scanner(System.in);
    }
    
    public void start(){
        boolean wantToPlay = false;
        do{
            // Prompt the user if they want the computer to keep guessing
            if (wantToPlay = prompt())
            {
                // Generate a random number for the computer to guess
                generatedNumber = super.randGenNum();
                // Start the game
                playGame();
            } 
            
        } while (!wantToPlay);
        
        
        
    }
    
    private void playGame()
    {
        boolean done = false;
        int min = 1;
	int max = 100;
        int count = 0;
        String ans = "";
        
        while(!done)
        {
            // Generate a random guess within the range
            int guess = min + (int)(Math.random() * (max - min + 1));
            count++;
            
            System.out.println("I guess " + guess);
            
            if (guess > generatedNumber) {
                System.out.println("lower");
                max = guess - 1;
                break;
            } else if (guess < generatedNumber) {
                System.out.println("higher");
                min = guess + 1;
                break;
            } else {
                System.out.println("I guessed the right number in " + count + "guesses\n\n");
                done = true;
            }
             

    }
    
   
    }
    private boolean prompt()
    {
        boolean answer = false;
        boolean inputOk = false;
        while (!inputOk) {
             // Prompt the user for their choice
            System.out.print("Do you want the computer to keep guessing: Yes / No : ");
            String input = scan.nextLine();
            if (input.equalsIgnoreCase("y") || input.equalsIgnoreCase("yes")) {
                inputOk = true;
                answer = true;
            } else if (input.equalsIgnoreCase("n")|| input.equalsIgnoreCase("no")) {
                inputOk = true;
                answer = false;
            } else {
                System.out.println(
                        "Ohh come on. Even Mr. Bean knows where are 'y' and 'n' in the keyboard?? Please try again:");
            }
        }
        return answer;
    }
}
