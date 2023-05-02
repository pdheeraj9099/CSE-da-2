# CSE-da-2

#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() {
 char str[100];
 int vowels = 0, consonants = 0, spaces = 0, specialChars = 0, words =
1;
 printf("Enter a string: ");
 fgets(str, sizeof(str), stdin);
 for (int i = 0; str[i] != '\0'; i++) {
 if (isspace(str[i])) {
 spaces++;
 words++;
 } else if (isalpha(str[i])) {
 if (str[i] == 'a' || str[i] == 'e' || str[i] == 'i' || str[i]
== 'o' || str[i] == 'u' ||
 str[i] == 'A' || str[i] == 'E' || str[i] == 'I' || str[i]
== 'O' || str[i] == 'U') {
 vowels++;
 } else {
 consonants++;
 }
 } else {
 specialChars++;
 }
 }
 printf("Words = %d\n", words);
 printf("Vowels = %d\n", vowels);
 printf("Consonants = %d\n", consonants);
 printf("Space = %d\n", spaces);
 printf("Special Characters = %d\n", specialChars);
 return 0;
} 
