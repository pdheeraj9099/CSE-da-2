# CSE-da-2

#include <stdio.h>
#include <string.h>
int main() {
 char str[100];
 int len, freq[256] = {0}, i;
 char *first_rep = NULL, *first_nonrep = NULL;
 printf("Enter a string: ");
 fgets(str, 100, stdin);
 len = strlen(str) - 1;
 for(i = 0; i < len; i++) {
 freq[(int)str[i]]++;
 }
 printf("Length of the string is: %d\n", len);
 printf("Word frequency is: ");
 for(i = 0; i < 256; i++) {
 if(freq[i] != 0) {
 printf("%c:%d ", i, freq[i]);
 }
 }
 printf("\n");
 for(i = 0; i < len; i++) {
 if(freq[(int)str[i]] > 1 && first_rep == NULL) {
 first_rep = &str[i];
 } else if(freq[(int)str[i]] == 1 && first_nonrep == NULL) {
 first_nonrep = &str[i];
 }
 if(first_rep != NULL && first_nonrep != NULL) {
 break;
 }
 }
 if(first_rep == NULL) {
 printf("No repeated characters found in the string.\n");
 } else {
 printf("First repeated character is: %c\n", *first_rep);
 }
 if(first_nonrep == NULL) {
 printf("No non-repeated characters found in the string.\n");
 } else {
 printf("First non-repeated character is: %c\n", *first_nonrep);
 }
 return 0;
} 
