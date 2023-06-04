# Hi-Lo

import java.util.Scanner;
import java.util.Scanner;


public class HIiLoProject {


    public static void main(String[] args)  {
        // Create a scanner object to read user input
        Scanner scan = new Scanner(System.in);
        String input;
        
        // Prompt the user to choose a game mode
        System.out.println("Do you want to play single player (s), two player (t)"
                + ", or watch the computer (c) play?");
        input = scan.nextLine();
        
         // Check the user's input and start the corresponding game mode
        if (input.equals("s")){
            // Create a HiLo object for single player mode and start the game
            HiLo onePlayer = new HiLo();
            onePlayer.start();
        }
        
        if (input.equals("t")){
            // Create a TwoPlayerGame object for two player mode and start the game
            TwoPlayerGame twoPlayer = new TwoPlayerGame();
            twoPlayer.start();
        }
        
        if (input.equals("c")){
            // Create a ComputerPlayer object to watch the computer play and start the game
            ComputerPlayer comp = new ComputerPlayer();
            comp.start();
        }
        
    }
    
}
