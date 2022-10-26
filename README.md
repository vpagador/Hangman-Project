# Hangman-Project
This is the Ai Core Hangman Project

## Milestone 1
- Pulled hangman template (with incomplete code) from Github to use as a starting point, with the TODOs as guide prompts representative of milestones. 

## Milestone 2
- TODO 1 is to ask user for input within the ask_letter method
- Used basic python functions and concepts such as a while loop, control flow, input and len()
```python
valid_input = False
while not valid_input:
    letter = input('Type in a letter: ') 
    if letter.isalpha() == True and len(letter) == 1:
       valid_input = True
       print(letter)
    elif letter.isalpha() == True and len(letter) != 1:
       print("Please, enter just one character")
```


## Milestone 3
- TODO 2 is to define the __init__ method for the Hangman class. Upon initialisation, two messages should be printed.  
- This required a background understanding of object-orientated programming (OOP), in which the __init__method serves as the initialiser for the class.
- Each attribute is set within __init__
- self.word_guessed is a list created to contain the missing letters of the word for the player to guess; missing letters represented by '_'.

```python
def __init__(self, word_list, num_lives=5):
    # TODO 2: Initialize the attributes as indicated in the docstring
    self.word_list = word_list
    self.num_lives = num_lives

    self.word = word_list[random.randint(0,len(word_list)-1)]
    self.word_guessed = []
    self.list_letters = []
    self.num_letters = 0

    for i in self.word:
        self.word_guessed.append('_') 
    # TODO 2: Print two message upon initialization:
    # 1. "The mystery word has {len(self.word)} characters" (The number of letters is NOT the UNIQUE number of letters)
    print(f"The mystery word has {len(self.word)} characters")
    # 2. {word_guessed}
    print(self.word_guessed)
    pass
```

## Milestone 4
- TODO 3 is to code the logic for the check letter method
- If the inputted letter is in the word, a for loop is used to loop over the range of the length of the word to obtain the index with which to replace the '_' with the 
letter.
- Otherwise, it takes one life away from num_lives and calls the draw_hangman method which draws the hangman visuals of the game.
- Control flow and attributes set in __init__ (i.e., self.num_letters) are used.
```python
# TODO 3: Check if the letter is in the word. TIP: You can use the lower() method to convert the letter to lowercase
    if letter.lower() in self.word:
        print(f'Nice! {letter} is in the word!')
# TODO 3: If the letter is in the word, replace the '_' in the word_guessed list with the letter
correct_letter = False
for i in range(len(self.word)):
    if letter.lower() == self.word[i]:
        self.word_guessed[i] = letter.lower()
        correct_letter = True

print(self.word_guessed) 
# TODO 3: If the letter is in the word, the number of UNIQUE letters in the word that have not been guessed yet has to be reduced by 1
self.num_letters = len(set(self.word))
if correct_letter:
    self.num_letters -= 1
# TODO 3: If the letter is not in the word, reduce the number of lives by 1
else:
    self.num_lives -= 1
    self.draw_hangman()
# Be careful! A word can contain the same letter more than once. TIP: Take a look at the index() method in the string class
pass

```


## Milestone 5
- The final task is to code the game logic in the play_game method. 
- Within the method, an instance of the Hangman class is stored in a variable called game.
- The logic is to keep asking the user for an input until either the answer is achieved or the number of lives reaches 0.
- A while loop and if/else statements are used in this case to keep calling game.ask_letter until said conditions are met, ending the game.
```python
def play_game(word_list):
    # As an aid, part of the code is already provided:
    game = Hangman(word_list, num_lives=5)
    # TODO 1: To test this task, you can call the ask_letter method
    # TODO 2: To test this task, upon initialization, two messages should be printed 
    # TODO 3: To test this task, you call the ask_letter method and check if the letter is in the word
    # TODO 4: Iteratively ask the user for a letter until the user guesses the word or runs out of lives
    while game.num_lives > 0 and '_' in game.word_guessed:
        game.ask_letter()
    # If the user guesses the word, print "Congratulations, you won!"
    if game.num_lives != 0:
        print('Congratulations you won!')
    # If the user runs out of lives, print "You ran out of lives. The word was {word}"
    else:
        print(f"You ran out of lives. The word was {game.word}")

    pass

```

- For added functionality, a hangman visual is created using the draw_hangman method which is called when a wrong letter is inputted. 
- Control flow is used to print the 5 body parts that represent lives lost in the game in progression:

```python
def draw_hangman(self):
    if self.num_lives == 4:
        print('\n0')
    elif self.num_lives == 3:
        print('\n 0')
        print('<\n')
    elif self.num_lives == 2:
        print('\n 0')
        print('< >\n')
    elif self.num_lives == 1:
        print('\n 0')
        print('< >')
        print(' /\n')
    elif self.num_lives == 0:
        print('\n 0')
        print('< >')
        print(' /\\\n')

```


## Conclusion
- This project is a programming exercise in Python that uses basic concepts such as control flow, method defintion and loops as well as more 
advanced concepts such as OOP.


