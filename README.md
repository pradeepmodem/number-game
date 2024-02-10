import java.util.Random;
import java.util.Scanner;

public class NumberGame {
    public static void main(String[] args) {
        Scanner input=new Scanner(System.in);
        numberGame();

        while(true){
            System.out.println();
            System.out.println("press x to play again!\nOr press anything else to stop!");
            char x=input.next().charAt(0);
            if(x=='x'){
                numberGame();
            }
            else{
                break;
            }
        }
    }
    public static void numberGame(){
        Scanner input=new Scanner(System.in);
        Random randInt=new Random();

        // adding 1 so that it will generate numbers from 1 to 100 instead of 0 to 99
        int randomNumber=randInt.nextInt(100)+1;
        System.out.println("You have 10 attempts to guess the number!");
        int score=10;

        for(int i=score;i>=0;i--){
            System.out.print("Guess the System generated number (1-100):");
            int userNum=input.nextInt();

            if(userNum==randomNumber){
                System.out.println();
                System.out.println("Correct Guess! You Won!");
                System.out.println("Your final score out of 10: "+ score);
                return;
            }

            else if(userNum>randomNumber){
                System.out.println("Too High!");
            }

            else{
                System.out.println("Too Low!");
            }
            score--;
        }

        if(score<=0){
            System.out.println("Oops! You Lost!");
            System.out.println("The correct number was: "+ randomNumber);
        }
    }
}
