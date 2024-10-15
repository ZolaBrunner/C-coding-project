# 🎃 Halloween Secret Message Challenge 🎃

Welcome to the **Halloween Secret Message Challenge** project by CodeFirst Girls, In partnership with: GCHQ.

This project implements a **Caesar Cipher** encryption system using **C++** to encode and decode secret messages, with a Halloween twist! 🧙‍♀️🦇

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Caesar Cipher Encoder](#caesar-cipher-encoder)
- [Play Again](#play-again)
- [Recursive Alternative](#recursive-alternative)
- [License](#license)
- [Project Management](#project-management)

---

## Project Overview
This project showcases a Caesar Cipher encryption algorithm written in **C++** that shifts letters in a message by a given number of positions in the alphabet. The goal is to send secret messages using a Halloween theme, adding a fun and spooky touch to the classic cipher.

---

## Features
- 🛠 **Encrypt and Decrypt Messages**: Encode or decode your secret message with Caesar Cipher by providing a shift value.
- 🎃 **Halloween-Themed UI**: User interface with spooky Halloween characters like vampires and witches to enhance user experience.
- 📜 **Shift Letters or Keep Non-Letters**: Shifts letters only, while keeping numbers, spaces, and punctuation unchanged.
- ⚡ **Real-Time Encryption and Decryption**: Enter a message and instantly see the encrypted or decrypted result.

---

## How to Use

### Encrypting a Message
1. Input your secret message in the designated text area.
2. Enter the desired shift value.
3. Click the "Encrypt" button to see your encoded message!

### Decrypting a Message
1. Paste your encoded message into the text area.
2. Enter the same shift value used for encryption.
3. Click the "Decrypt" button to reveal the original message.


---

## Project Management

Navigate to the project directory found on JIRA


---

## Caesar Cipher Encoder


#include <iostream>
// Include the string header
#include <string>
// Include the limits header for std::numeric_limits
#include <limits> // We researched this header and found it to be helpful for the user to know what the max and min values of the integer data type are 

// Function to encode a message using Caesar Cipher
std::string caesarCipher(std::string message, int shift) {
  std::string encodedMessage = "";
  for (int i = 0; i < message.length(); i++) {
    char ch = message[i];
    if (isalpha(ch)) {
      char base = islower(ch) ? 'a' : 'A';
      ch = (ch - base + shift) % 26 + base;
    }
    encodedMessage += ch;
  }
  return encodedMessage;
}

int main() {
  std::cout << "Welcome to the Halloween Secret Message Service!" << std::endl;

  // Choose a character
  std::cout << "Choose your character to help send your secret message:"
            << std::endl;
  std::cout << "1. Witch \n"
            << "2. Vampire \n"
            << "3. Ghost \n"
            << "4. Bat \n"
            << "5. Werewolf \n"
            << std::endl;
  std::cout << "Enter the number of your character choice: " << std::endl;

  // Assign character based on user choice
  // Initialize choice without a default value
  int choice;
  // Get user input for choice
  std::cin >> choice;

  // Display the selected character
  switch (choice) {
  case 1:
    std::cout << "You chose: Witch" << std::endl;
    break;
  case 2:
    std::cout << "You chose: Vampire" << std::endl;
    break;
  case 3:
    std::cout << "You chose: Ghost" << std::endl;
    break;
  case 4:
    std::cout << "You chose: Bat" << std::endl;
    break;
  case 5:
    std::cout << "You chose: Werewolf" << std::endl;
        break;
      default:
        std::cout << "Invalid choice!" << std::endl;
        return 1;
        // Exit the program if the choice is invalid
      }

      // Clear the input buffer before taking string input
      std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');

      // Get message from user
      std::cout << "Enter your spooky message: " << std::endl;
      std::string message;
      getline(std::cin, message); // Use getline to read the entire line

      // Get shift value from user
      int shift;
      std::cout << "Enter the shift value: " << std::endl;
      std::cin >> shift;

      // Encode the message
      std::string encodedMessage = caesarCipher(message, shift);

      // Display the encoded message
      std::cout << "\nYour secret Halloween message is: " << encodedMessage << " "
                << std::endl;


    }
---
## Play Again

#include <iostream>
// Include the string header
#include <string>
// Include the limits header for std::numeric_limits
#include <limits> // We researched this header and found it to be helpful for the user to know what the max and min values of the integer data type are 

// Function to encode a message using Caesar Cipher
std::string caesarCipher(std::string message, int shift) {
  std::string encodedMessage = "";
  for (int i = 0; i < message.length(); i++) {
    char ch = message[i];
    if (isalpha(ch)) {
      char base = islower(ch) ? 'a' : 'A';
      ch = (ch - base + shift) % 26 + base;
    }
    encodedMessage += ch;
  }
  return encodedMessage;
}

int main() {
  char playAgain; 
  do{
  std::cout << "Welcome to the Halloween Secret Message Service!" << std::endl; 

  
  // Choose a character
  std::cout << "Choose your character to help send your secret message:"
            << std::endl;
  std::cout << "1. Witch \n"
            << "2. Vampire \n"
            << "3. Ghost \n"
            << "4. Bat \n"
            << "5. Werewolf \n"
            << std::endl;
  std::cout << "Enter the number of your character choice: " << std::endl;

  // Assign character based on user choice
  // Initialize choice without a default value
  int choice;
  // Get user input for choice
  std::cin >> choice;

  // Display the selected character
  switch (choice) {
  case 1:
    std::cout << "You chose: Witch" << std::endl;
    break;
  case 2:
    std::cout << "You chose: Vampire" << std::endl;
    break;
  case 3:
    std::cout << "You chose: Ghost" << std::endl;
    break;
  case 4:
    std::cout << "You chose: Bat" << std::endl;
    break;
  case 5:
    std::cout << "You chose: Werewolf" << std::endl;
        break;
      default:
        std::cout << "Invalid choice!" << std::endl;
        return 1;
        // Exit the program if the choice is invalid
      }

      // Clear the input buffer before taking string input
      std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');

      // Get message from user
      std::cout << "Enter your spooky message: " << std::endl;
      std::string message;
      getline(std::cin, message); // Use getline to read the entire line

      // Get shift value from user
      int shift;
      std::cout << "Enter the shift value: " << std::endl;
      std::cin >> shift;

      // Encode the message
      std::string encodedMessage = caesarCipher(message, shift);

      // Display the encoded message
      std::cout << "\nYour secret Halloween message is: " << encodedMessage << " "
                << std::endl;

     // Ask if the user wants to play again
          std::cout << "\nWould you like to play again? (y/n): ";
std::cin >> playAgain;
    }while(playAgain=='Y'||playAgain=='y');
}

---
## Recursive Alternative


---
## Recursive Alternative Play Again

---

## License

MIT


