# CodeAlpha_NumberGuessingGame
This repository contains a simple number guessing game implemented in C++. The computer randomly selects a number between 1 and 100, and the player has to guess it. After each guess, the game provides hints to help the player, such as "Too high!" or "Too low!".

Features
Random number generation
Interactive guessing with user input
Hints to guide the player
Tracks the number of attempts

The game is implemented in a single file, guessing_game.cpp. It includes:
Random Number Generation: The program generates a random number between 1 and 100 using std::rand() and std::srand().
Game Loop: The game continues to prompt the player for a guess until they correctly guess the number.
Hints: After each guess, the program provides feedback ("Too high!" or "Too low!") to guide the player towards the correct number.
Attempts Counter: The program keeps track of the number of attempts taken to guess the number.
----------------------------------------------------------------------------------------------------------------------------------
#include<iostream>
#include<cstdlib>
#include<ctime>

int main() {
    std::srand(static_cast<unsigned int>(std::time(nullptr)));
    int numberToGuess = std::rand() % 100 + 1; // Random number between 1 and 100
    int playerGuess = 0;
    int attempts = 0;

    std::cout << "Welcome to the World Of Number Guessing Game!" << std::endl;
    std::cout << "We have selected a number between 1 and 100. Can you guess it?" << std::endl;

    // Game loop
    while (playerGuess != numberToGuess) {
        std::cout << "Enter your guess: ";
        std::cin >> playerGuess;
        attempts++;

        if (playerGuess > numberToGuess) {
            std::cout << "Too high! Try again." << std::endl;
        } else if (playerGuess < numberToGuess) {
            std::cout << "Too low! Try again." << std::endl;
        } else {
            std::cout << "Congratulations Player! You guessed the number in " << attempts << " attempts." << std::endl;
        }
    }

    return 0;
}

