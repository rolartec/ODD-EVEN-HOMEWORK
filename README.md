ODD-EVEN-HOMEWORK
=================
// BY REINA OLARTE

//  ODD - EVEN  GAME HOMEWORK WEEK # 9

import java.util.Scanner;

public class OddEven 
{
	//  VARIABLES
	
		int RanNumber;
		int compNumber;
		int GameC;
		int GameW;
		int GameL;
		String Guess;
		String CompResult;
		String Play;
		String KeepPlay;
		//   
	boolean SIGA = true;
	
	Scanner input = new Scanner(System.in);

	public OddEven(String play)
	{
		if (play.toUpperCase().startsWith("Y"))
		{
			SIGA = true;
		}
		else
		{
			SIGA = false;
		}
	}
	
	
	public void displayMessage()
	{
		System.out.println("Hi!!! Welcome to the Odd / Even Game");

	}
	public void playGame()
	{

		while(SIGA)
		{
			RanNumber =  0 + (int)(Math.random() *10);
			
			compNumber = RanNumber % 2;
			
			if (compNumber == 1)
			{
				CompResult = "ODD";
			}
						else if (compNumber == 0)
			{
								CompResult = "EVEN";
			}
			System.out.println("Please Guess and write  Odd or Even: ");
			
			Guess = input.next();
			
			if(Guess.toUpperCase().equals(CompResult))
			{
				System.out.printf("YEA!!!! You won\nYou Guessed %s\nand the computer number was %d\n\n", Guess, RanNumber);
				
				++GameC;
				
				++GameW;
			}
			else
			{
				System.out.printf("OHHHH!!!!!You Lost\nYou Guessed %s\nComputer number was %d\n\n", Guess, RanNumber);
				
				++GameC;
				
				++GameL;
			}
			System.out.println("Do you want to keep Playing?");
			
			KeepPlay = input.next();
			
			if(KeepPlay.toUpperCase().startsWith("N"))
			{
				SIGA = false;
			}
		}//End while loop
	}//End Game method
	public void displayResults()
	{
		System.out.printf("Here are your results\nGames Played %d\nGames Won %d\nGames Lost %d\nThanks for playing", GameC, GameW, GameL);
	}
}//End Class

