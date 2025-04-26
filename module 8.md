EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
...python
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n < 0) {
        printf("Invalid input: Please enter a non-negative number.\n");
        return 1; 
    }
    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 13:
            printf("seventy three\n");
            break;
        case 14:
            printf("seventy four\n");
            break;
        case 15:
            printf("seventy five\n");
            break;
        case 16:
            printf("seventy six\n");
            break;
Output:
![image](https://github.com/user-attachments/assets/be56bc15-a11c-4d3c-959c-a79557182b0c)
Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
...python
#include <stdio.h>
int main() {
    char a[50];
    int h, c, i;
    printf("Enter the string (digits only): ");
    scanf("%s", a);
    for (h = 0; h <= 9; h++) {
        c = 0; 
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] == h + '0') { 
                c++;
            }
        }
        printf("%d ", c); 
    }
    printf("\n");
    return 0;
}
...
Output:
![image](https://github.com/user-attachments/assets/5def5cde-4227-4242-b6d7-0f756149161a)
Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
...python
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}
void reverse(char *str, int start, int end) {
    while (start < end) {
        swap(&str[start], &str[end]);
        start++;
        end--;
    }
}
int nextPermutation(char *str) {
    int i = strlen(str) - 2;
    while (i >= 0 && str[i] >= str[i + 1])
        i--;
    if (i < 0)
        return 0;
    int j = strlen(str) - 1;
    while (str[j] <= str[i])
        j--;
    swap(&str[i], &str[j]);
    reverse(str, i + 1, strlen(str) - 1);
    return 1;
}
int compareChars(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}
int main() {
    char *s;
    int n;
    s = (char *)malloc(100 * sizeof(char));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    printf("Enter the string: ");
    scanf("%s", s);
    qsort(s, strlen(s), sizeof(char), compareChars);
    do {
        printf("%s\n", s);
    } while (nextPermutation(s));
    free(s);
    return 0;
}
...
Output:
![image](https://github.com/user-attachments/assets/2b2b5b18-22b4-4634-ad0e-4d75245c78ed)
Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
...python
#include<stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    int l=n*2-1;
    for(int i=0;i<l;i++)
    {
        for(int j=0;j<l;j++)
        {
            int min=i<j ? i :j;
            min=min<l-i ? min:l-i-1;
            min=min< l-j-1 ?min: l-j-1;
            printf("%d ",n-min);
        }
        printf("\n");
    }
}
...
Output:
![image](https://github.com/user-attachments/assets/143cbe47-df3f-4e4e-8ed7-f2e2c71bf481)

Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
...python
#include <stdio.h>
int square() {
    int num, result;
    printf("Enter a number: ");
    scanf("%d", &num);
    result = num * num;
    return result;     
}
int main() {
    int sq;
    sq = square();
    printf("Square of the number is: %d\n", sq);
    return 0;
}
...
Output:
![image](https://github.com/user-attachments/assets/ac95ed33-1260-4fe4-b786-da61bf18ade4)
Result:
Thus, the program is verified successfully



























