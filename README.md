# CSE-da-2

>cC2 SLOT
>>>>>C1
#include <stdio.h>
void divide(int arr[], int left, int right, int* count);
int main() {
 int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
 int count = 0;
 divide(arr, 0, 9, &count);
 printf("Number of iterations: %d\n", count);
 return 0;
}
void divide(int arr[], int left, int right, int* count) {
 if (left == right) {
 return;
 }
 int mid = (left + right) / 2;
 divide(arr, left, mid, count);
 divide(arr, mid+1, right, count);
 (*count)++;
 printf("Iteration %d: left=%d, right=%d\n", *count, left, right);
}
>>>>>C2
#include <stdio.h>
#include <ctype.h>
int main() {
 char str[100];
 int counts[5] = {0};
 printf("Enter a string: ");
 fgets(str, 100, stdin);
 for (int i = 0; str[i] != '\0'; i++) {
 char c = str[i];
 if (isupper(c)) {
 counts[0]++;
 printf("%c is an uppercase alphabet.\n", c);
 }
 else if (islower(c)) {
 counts[1]++;
 printf("%c is a lowercase alphabet.\n", c);
 }
 else if (isdigit(c)) {
 counts[2]++;
 printf("%c is a digit.\n", c);
 }
 else if (isspace(c)) {
 counts[3]++;
 printf("%c is a whitespace.\n", c);
 }
 else {
 counts[4]++;
 printf("%c is a special symbol.\n", c);
 }
 }
 printf("Counts:\n");
 printf("Uppercase alphabet: %d\n", counts[0]);
 printf("Lowercase alphabet: %d\n", counts[1]);
 printf("Digit: %d\n", counts[2]);
 printf("Whitespace: %d\n", counts[3]);
 printf("Special symbol: %d\n", counts[4]);
 return 0;
}
>>>>>>C3
#include <stdio.h>
void findFactorial(int n, double* result) {
 double factorial = 1;
 for (int i = 1; i <= n; i++) {
 factorial *= i;
 }
 *result += factorial/n;
 if (n > 1) {
 findFactorial(n - 1, result);
 }
}
int main() {
 int n;
 double sum = 0;
 printf("Enter the value of n: ");
 scanf("%d", &n);
 findFactorial(n, &sum);
 printf("The sum of the series is: %.2lf", sum);
 return 0;
}
>>>>>C4
#include <stdio.h>
#include <string.h>
int main() {
 char type[10];
 float price, extra, discount, gst, net, total;
 printf("Enter the type of the car (Hatchback, Sedan, SUV, MUV): ");
 scanf("%s", type);
 printf("Enter the price of the car: ");
 scanf("%f", &price);
 printf("Enter the extra fitting price of the car: ");
 scanf("%f", &extra);
 total = price + extra;
 if (strcmp(type, "Hatchback") == 0) {
 discount = total * 0.03;
 }
 else if (strcmp(type, "Sedan") == 0) {
 discount = total * 0.05;
 }
 else if (strcmp(type, "SUV") == 0) {
 discount = total * 0.1;
 }
 else if (strcmp(type, "MUV") == 0) {
 discount = total * 0.15;
 }
 else {
 printf("Invalid Type\n");
 return 0;
 }
 gst = (total - discount) * 0.12;
 net = total - discount + gst;
 printf("Net amount to be paid: %.2f\n", net);
 return 0;
}
>>>>>C5
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int process_string(char* str);
int main() {
 char str[100];
 printf("Enter a sentence with two words: ");
 scanf("%[^\n]", str);
 int len = process_string(str);
 printf("Length of string: %d\n", len);
 return 0;
}
int process_string(char* str) {
 char first[50], second[50];
 int i = 0, j = 0, k = 0;
 while (str[i] != ' ') {
 first[j++] = toupper(str[i++]);
 }
 first[j] = '\0';
 i++;
 while (str[i] != '\0') {
 second[k++] = toupper(str[i++]);
 }
 second[k] = '\0';
 printf("%s %s\n", first, second);
 int len = strlen(str);
 printf("Length of revised string: %d\n", len);
 if (len < 20) {
 return len;
 }
 else {
 return sizeof(str);
 }
}
<<15 question>>
#include <stdio.h>
int main() {
int i, j, a, b, c, sum, acute = 0, right = 0, obtuse = 0, wrong = 0;
 for (i = 1; i <= 5; i++) {
 printf("Enter the three angles of triangle %d:\n",i);
 scanf("%d %d %d", &a, &b, &c);
 sum = a + b + c;
 if (sum > 180) {
 printf("Wrong Entry try again\n");
 wrong++;
 i--;
 continue;
 }
 if (a < b) {
 j = a;
 a = b;
 b = j;
 }
 if (a < c) {
 j = a;
 a = c;
 c = j;
 }
 if (a*a == b*b + c*c) {
 printf("Right-Angled Triangle\n");
 right++;
 } else if (a*a < b*b + c*c) {
 printf("Acute Angled Triangle\n");
 acute++;
 } else {
 printf("Obtuse Angled Triangle\n");
 obtuse++;
 }
 }
 printf("\nAcute Angled Triangle: %d\n", acute);
 printf("Right Angled Triangle: %d\n", right);
 printf("Obtuse Angled Triangle: %d\n", obtuse);
 printf("Wrong Entries: %d\n", wrong);
Â Â Â Â returnÂ 0;
} 
