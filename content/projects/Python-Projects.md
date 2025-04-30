+++
date = '2025-04-25T14:00:47+01:00'
draft = false
title = 'Collaborative Python Projects to Explore the Foundation of Machine Learning'
+++

Machine learning is a powerful tool for extracting the best insights from a dataset and accurately predicting future outcomes. New applications of machine learning models are created daily that have a real impact across various industries. 

Because of this, my friend and I were eager to learn more about machine learning, but we didn’t know where to start. My friend came across an article that said that Python is the foundation of machine learning, so it is crucial to have a grasp on the concepts of Python first - [The Ultimate Beginner to Advance guide to Machine learning](https://pub.towardsai.net/the-ultimate-beginner-to-advance-guide-to-machine-learning-b4dd361aefbb)

Therefore, over the past few months, we have worked through a list of Python projects to become more confident with the different aspects of Python. Here are a few of the projects we have completed:

---

### 21 Game

The 21 game is a game where you lose if you say the number 21 or over. The first player says the number 1, 2 or 3. The next player then says 4, 5 or 6, and so on. The person who says 21 loses. In our Python version of this game, we made it so that one player plays against the computer. Here is an example of the game:

![21_gameplay](/img/21_gameplay.png)

For this game, we had to have a strategy for whether the computer would say add 1, 2 or 3 to the current number based on what number the player added. This would take up a lot of room in the code, so we created a function to make this strategy one line in the code of the game, with another section to define the function elsewhere in the code.

![21_game_1](/img/21_game_1.png)


![21_game_2](/img/21_game_2.png)


![21_game_3](/img/21_game_3.png)

The best strategy for this game is to add to the current number to make it a multiple of four on your turn because this guarantees that you will say the number 20, making you opponent say 21 to lose. However, if your opponent is saying the multiples of four, there is nothing to be done and you have effectively lost. I have reflected this in the `strategy` function that I made. This project was great practice in defining and using functions, as well as using `while` loops with the `break` and `continue` statements.

---

### PDF comparison Tool

The task in this project was for the program to take in 2 PDF files and judge whether the content of the files are identical. To make this program applicable to larger files, we wrote the code so that it read the pdf file in chunks at a time and converted the content of the code into a hexadecimal hash value using hashlib. This hash value allows easy comparison between the 2 files.

![pdf_compare_1](/img/pdf_compare_1.png) 

This was my fist experience using hashlib. I find it interesting that the encryption algorithms like SHA-1 have been cryptographically broken, but they are still useful for programs like the one my friend and I made. I also learned about reading binary and the ability to do this in chunks so that the program can handle large datasets.

---

### Mastermind Game

Mastermind is a game where one player chooses a number and the opponent has to guess the number. When the guesser guesses a number, they get a red pin for every digit from the guess that they got correct, but in the wrong place in the number to guess, and a black pin for every number they got right in the right place in the number to guess. It's a bit like wordle but with numbers. Here is a round of the game being played:

![mastermind_gameplay](/img/mastermind_gameplay.png)

Here is the code for the game:

![mastermind](/img/mastermind.png)

So that the computer chose 4 distinct numbers, I found the `string` package which contains `string.digits` which is a string of numbers from 0 to 9, and I used `random.sample()` to create a list of 4 random numbers from this string. To compare the set number with the player's guess, I turned the guess into a list of digits using list comprehension. This project was great practice in using list comprehension and using the `string` package.


