# Hangman-Project
This is the Ai Core Hangman Project

## Milestone 1
- Pulled hangman template (with incomplete code) from Github to use as a starting point, with the TODOs as guide prompts representative of milestones. 

## Milestone 2
- TODO 1 is to ask user for input within the ask_letter method
- Used basic python functions and concepts such as a while loop, control flow, input and len()
<img width="327" alt="image" src="https://user-images.githubusercontent.com/80417833/187993441-bcf660e4-a562-42a0-be84-4dbd8af33048.png">


## Milestone 3
- TODO 2 is to define the __init__ method for the Hangman class. Upon initialisation, two messages should be printed.  
- This required a background understanding of object-orientated programming (OOP), in which the __init__method serves as the initialiser for the class.
- Each attribute is set within __init__
- self.word_guessed is a list created to contain the missing letters of the word for the player to guess; missing letters represented by '_'.
<img width="689" alt="image" src="https://user-images.githubusercontent.com/80417833/187994741-fd9bdec3-31df-47c1-b1db-fb69ed5ec6ea.png">


## Milestone 4
- TODO 3 is to code the logic for the check letter method
- If the inputted letter is in the word, a for loop is used to loop over the range of the length of the word to obtain the index with which to replace the '_' with the 
letter.
- Otherwise, it takes one life away from num_lives and calls the draw_hangman method which draws the hangman visuals of the game.
- Control flow and attributes set in __init__ (i.e., self.num_letters) are used.
<img width="780" alt="image" src="https://user-images.githubusercontent.com/80417833/187995036-df55198c-608b-45bc-bfc3-930869bccd87.png">


## Milestone 5
- The final task is to code the game logic in the play_game method. 
- Within the method, an instance of the Hangman class is stored in a variable called game.
- The logic is to keep asking the user for an input until either the answer is achieved or the number of lives reaches 0.
- A while loop and if/else statements are used in this case to keep calling game.ask_letter until said conditions are met, ending the game.
<img width="605" alt="image" src="https://user-images.githubusercontent.com/80417833/187996477-a2bff4f5-a312-4f10-8d4e-f2c6c1099748.png">

- For added functionality, a hangman visual is created using the draw_hangman method which is called when a wrong letter is inputted. 
- Control flow is used to print the 5 body parts that represent lives lost in the game in progression:

<img width="175" alt="image" src="https://user-images.githubusercontent.com/80417833/187996383-c7c1a16f-3627-4173-984b-b8f338ec96bc.png">


## Conclusion
- This project is a programming exercise in Python that uses basic concepts such as control flow, method defintion and loops as well as more 
advanced concepts such as OOP.


