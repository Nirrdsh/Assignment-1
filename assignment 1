#include <stdio.h>
#include <string.h>
#include "helpers.h"
#include <stdbool.h>

char caesar_left(char c, int shift) {
    return (c - shift);
}

char caesar_right(char c, int shift) {
    return (c + shift);
}

int main() {
    char operation[10];
    char encryption[10];
    char decryption[10];
    char choice[10];
    char word[100];
    char key[100];
    int offset;
    string name = get_string("Please enter your name.\n");
    printf("Welcome %s!\n", name);
    bool is_running = false;
    while (!is_running) {
        printf("Do you want to encode or decode a message? : ");
        scanf("%s", operation);
        if (operation[0] == 'e' || operation[0] == 'd') {
            is_running = true;
        } else {
            printf("Invalid operation. Please enter 'e' for encoding or 'd' for decoding.\n");
        }
    }
    if (operation[0] == 'e') {
        printf("which method you want to use?:");
        scanf("%s", encryption);
        if (encryption[0] == 'c') 
        {
            printf("choose left or right:");
            scanf("%s", choice);
            printf("please enter offset:");
            scanf("%d", &offset);
            if (choice[0] == 'l') {
                printf("Enter a word: ");
                scanf("%s", word);
                int length = strlen(word);
                char caesar[length + 1];
                for (int i = 0; i < length; i++) {
                    caesar[i] = caesar_left(word[i], offset);
                }
                caesar[length] = '\0';
                printf("Encrypted word is %s\n", caesar);
            }
            else if (choice[0] == 'r') {
                printf("Enter the word: ");
                scanf("%s", word);
                int length = strlen(word);
                char caesar[length + 1];
                for (int i = 0; i < length; i++) {
                    caesar[i] = caesar_right(word[i], offset);
                }    
                caesar[length] = '\0';
                printf("encrypted word: %s\n", caesar);
            }
        } 
         else if (encryption[0] == 'v')
        {
            printf("Enter a word: ");
            scanf("%s", word);
            int length = strlen(word);
            printf("Enter the keyword: ");
            scanf("%s", key);
            int keyword_length = strlen(key);
            char vigenere[length + 1];
            for (int i = 0; i < length; i++) {
               int shift = key[i % keyword_length] - 'a';
               char encrypted_char = ((word[i] - 'a' + shift) % 26) + 'a';
               vigenere[i] = encrypted_char;
            }   
            vigenere[length] = '\0';
            printf("encrypted word: %s\n", vigenere);

        }
        else if (encryption[0] == 's')
        {
            printf("choose left or right:");
            scanf("%s", choice);
            printf("please enter offset:");
            scanf("%d", &offset);
            int salt_value = 0;
            for (int i = 0; i < strlen(name); i++) {
                salt_value += (int) name[i];
            }
        
            if (choice[0] == 'l') {
                printf("Enter a word: ");
                scanf("%s", word);
                int length = strlen(word);
                char caesar[length + 1];
                for (int i = 0; i < length; i++) {
                    caesar[i] = caesar_left(word[i], offset + salt_value);
                }
                caesar[length] = '\0';
                printf("Encrypted word is %s\n", caesar);
            }
            else if (choice[0] == 'r') {
                printf("Enter the word: ");
                scanf("%s", word);
                int length = strlen(word);
                char caesar[length + 1];
                for (int i = 0; i < length; i++) {
                    caesar[i] = caesar_right(word[i], offset + salt_value);
                }    
                caesar[length] = '\0';
                printf("encrypted word: %s\n", caesar);
            }
        }            
    }else if (operation[0] == 'd')
        {
            printf("which method do you want to use?:");
            scanf("%s", decryption);

            if (decryption[0] == 'c')
            {
                printf("choose left or right:");
                scanf("%s", choice);
                printf("please enter offset:");
                scanf("%d", &offset);
                if (choice[0] == 'l')
                {
                  printf("Enter the encrypted word: ");
                  scanf("%s", word);
                  int length = strlen(word);
                  char caesar[length + 1];
                  for (int i = 0; i < length; i++) {
                    caesar[i] = caesar_right(word[i], offset);
                    }    
                   caesar[length] = '\0';
                   printf("Decrypted word: %s\n", caesar);
                }
                else if (choice[0] == 'r')
                {
                    printf("Enter a encrypted word: ");
                    scanf("%s", word);
                    int length = strlen(word);
                    char caesar[length + 1];
                    for (int i = 0; i < length; i++) {
                    caesar[i] = caesar_left(word[i], offset);
                    }
                    caesar[length] = '\0';
                    printf("decrypted word is: %s\n", caesar);
                }
                 
            }
            else if (decryption[0] == 'v')
            {
                printf("Enter a encrypted word: ");
                scanf("%s", word);
                int length = strlen(word);
                printf("Enter the key: ");
                scanf("%s", key);
                int keyword_length = strlen(key);
                char vigenere[length + 1];
                for (int i = 0; i < length; i++) {
                    int shift = key[i % keyword_length] - 'a';
                    char decrypted_char = ((word[i] - 'a' - shift + 26) % 26) + 'a';
                    vigenere[i] = decrypted_char;
                }   
                vigenere[length] = '\0';
                printf("decrypted word: %s\n", vigenere);
               
            }
            else if (decryption[0] == 's')
            {
               printf("choose left or right:");
            scanf("%s", choice);
            printf("please enter offset:");
            scanf("%d", &offset);
            int salt_value = 0;
            for (int i = 0; i < strlen(name); i++) {
                salt_value += (int) name[i];
            }
        
            if (choice[0] == 'l') {
                printf("Enter a word: ");
                scanf("%s", word);
                int length = strlen(word);
                char salted_caesar[length + 1];
                for (int i = 0; i < length; i++) {
                    salted_caesar[i] = caesar_right(word[i], offset + salt_value);
                }
                salted_caesar[length] = '\0';
                printf("decrypted word is %s\n", salted_caesar); 
            }else if (choice[0] == 'r')
            {
                 printf("Enter the word: ");
                scanf("%s", word);
                int length = strlen(word);
                char salted_caesar[length + 1];
                for (int i = 0; i < length; i++) {
                    salted_caesar[i] = caesar_left(word[i], offset + salt_value);
                }    
                salted_caesar[length] = '\0';
                printf("encrypted word: %s\n", salted_caesar);
            }
            }
                
        
    /*}else 
    printf("please try again\n");*/
    
return 0;    
}}
