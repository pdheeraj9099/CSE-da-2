# CSE-da-2

 CAT 1B
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
typedef struct {
 char name[50];
 int age;
 char position[50];
 char date_of_joining[11];
} Employee;
int cmp_name(const void* a, const void* b) {
 return strcmp(((Employee*)a)->name, ((Employee*)b)->name);
}
int cmp_date(const void* a, const void* b) {
 return strcmp(((Employee*)a)->date_of_joining, ((Employee*)b)-
>date_of_joining);
}
int main() {
 int num_employees;

 printf("Enter the number of employees: ");
 scanf("%d", &num_employees);

 Employee* employees = (Employee*) malloc(num_employees *
sizeof(Employee));

 for (int i = 0; i < num_employees; i++) {
 printf("Enter details of employee %d:\n", i+1);
 printf("Name: ");
 scanf("%s", employees[i].name);
 printf("Age: ");
 scanf("%d", &employees[i].age);
 printf("Position: ");
 scanf("%s", employees[i].position);
 printf("Date of joining (dd/mm/yyyy): ");
 scanf("%s", employees[i].date_of_joining);
 }

 qsort(employees, num_employees, sizeof(Employee), cmp_name);

 printf("\nEmployee List sorted by name:\n");
 for (int i = 0; i < num_employees; i++) {
 printf("Name: %s\n", employees[i].name);
 printf("Age: %d\n", employees[i].age);
 printf("Position: %s\n", employees[i].position);
 printf("Date of Joining: %s\n\n", employees[i].date_of_joining);
 }

 qsort(employees, num_employees, sizeof(Employee), cmp_date);

 printf("\nEmployee List sorted by date of joining:\n");
 for (int i = 0; i < num_employees; i++) {
 printf("Name: %s\n", employees[i].name);
 printf("Age: %d\n", employees[i].age);
 printf("Position: %s\n", employees[i].position);
 printf("Date of Joining: %s\n\n", employees[i].date_of_joining);
 }
 free(employees);
 return 0;
}
G2 SLOT:::
>>>>>G1:::
#include <stdio.h>
int main() {
 float chennai[7], delhi[7], haveri[7], gangtok[7];
 float chennai_temp, delhi_temp, haveri_temp;
 int i;
 printf("Enter the temperature of Chennai for a week of 7 days:\n");
 for (i = 0; i < 7; i++) {
 scanf("%f", &chennai[i]);
 }
 for (i = 0; i < 7; i++) {
 delhi[i] = chennai[i] - 8;
 haveri[i] = chennai[i] + 5;
 }
 for (i = 0; i < 7; i++) {
 gangtok[i] = haveri[i] - delhi[i];
 }
 printf("Temperature of Gangtok for a week of 7 days:\n");
 for (i = 0; i < 7; i++) {
 printf("%.2f ", gangtok[i]);
 }
 printf("\n");
 return 0;
}
>>>>>G2
#include <stdio.h>
int sumOfDigits(int n) {
 int sum = 0;
 while (n > 0) {
 sum += n % 10;
 n /= 10;
 }
 return sum;
}
int main() {
 int sum = 0;
 for (int i = 1000; i <= 9998; i += 2) {
 sum += i;
 }
 while (sum > 9) {
 sum = sumOfDigits(sum);
 }
 if (sum % 2 == 0) {
 printf("Even found\n");
 } else {
 printf("Odd found\n");
 }
 return 0;
}
>>>>> G3
#include <stdio.h>
#include <string.h>
int main()
{
 char password[] = "aeiceg";
 char input[3][3];
 char diagonal[5];
 int i, j, k = 0;

 printf("Enter the input characters:\n");
 for(i=0; i<3; i++)
 {
 for(j=0; j<3; j++)
 {
 scanf(" %c", &input[i][j]);
 }
 }

 diagonal[k++] = input[0][0];
 diagonal[k++] = input[1][1];
 diagonal[k++] = input[2][2];
 diagonal[k++] = input[0][2];
 diagonal[k] = input[2][0];

 if(strcmp(diagonal, password) == 0)
 {
 printf("Password matched. The locker is opened successfully.\n");
 }
 else
 {
 printf("Password not matched. The locker cannot be opened.\n");
 }

 return 0;
}
>>>>>G4
#include <stdio.h>
int main() {
 int original_marks[25], revised_marks[25], birth_month[25];
 float original_total = 0, revised_total = 0, original_avg,
revised_avg;
 printf("Enter original marks and birth month for each
student:\n");
 for(int i=0; i<25; i++) {
 printf("Student %d: ", i+1);
 scanf("%d %d", &original_marks[i], &birth_month[i]);
 }

 for(int i=0; i<25; i++) {
 revised_marks[i] = original_marks[i] + birth_month[i];
 original_total += original_marks[i];
 revised_total += revised_marks[i];
 }

 original_avg = original_total / 25;
 revised_avg = revised_total / 25;

 printf("Class average for original marks: %.2f\n", original_avg);
 printf("Class average for revised marks: %.2f\n", revised_avg);

 if(revised_avg - original_avg >= 5) {
 printf("Can implement - Significant increase in class
average.\n");
 } else {
 printf("Need not implement - No significant increase in class
average.\n");
 }

 return 0;
}
>>>>>G5
#include <stdio.h>
int power(int x, int n);
int main() {
 int x, n, result;

 printf("Enter a number x: ");
 scanf("%d", &x);

 printf("Enter a number n (less than or equal to 5): ");
 scanf("%d", &n);

 result = power(x, n);

 printf("%d to the power of %d is %d\n", x, n, result);

 return 0;
}
int power(int x, int n) {
 if (n == 0) {
 return 1;
 } else {
 return x * power(x, n-1);
 }
}
