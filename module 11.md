```python
Developed By  :  GURUSHARAN S
Register No   :  212224060088
Module No     :  C Module 11
```
EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```python
#include<stdio.h>
int add(int a,int b,int c,int d)
{
    if((a>b)&&(a>c)&&(a>d))
      return a;
    else if((b>c)&&(b>d))
      return b;
    else if(c>d)
      return c;
    else
      return d;
}
int main()
{
    int a,b,c,d;
    scanf("%d %d %d %d",&a,&b,&c,&d);
    int max=add(a,b,c,d);
    printf("%d",max);
}
```
Output:

![image](https://github.com/user-attachments/assets/9e2c14ad-66ed-4724-8d61-7c944c841fbd)


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```python
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0; 
    int o = 0; 
    int x = 0; 
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;
            if (and_val < k && and_val > a) {
                a = and_val;
            }
            if (or_val < k && or_val > o) {
                o = or_val;
            }
            if (xor_val < k && xor_val > x) {
                x = xor_val;
            }
        }
    }
    printf("Maximum AND value: %d\n", a);
    printf("Maximum OR value: %d\n", o);
    printf("Maximum XOR value: %d\n", x);
}
int main() {
    int n, k;
    printf("Enter two integers n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/58171ded-a0ea-45ef-88f2-16accee06b48)


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```python
#include <stdio.h>
#include <stdlib.h>
int main() {
    int noshel, noque;
    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);
    int** shelarr = (int**)malloc(noshel * sizeof(int*));
    int* nobookarr = (int*)calloc(noshel, sizeof(int));
    for (int i = 0; i < noshel; i++) {
        shelarr[i] = NULL;
    }
    int k, c;
    k = c = 0; 
    for (int i = 0; i < noque; i++) {
        int type_of_query;
        printf("\nEnter query type (1 to add, 2 to get pages, 3 to get number of books): ");
        scanf("%d", &type_of_query);
        if (type_of_query == 1) {
            int shelf, pages;
            printf("Enter shelf index and number of pages: ");
            scanf("%d %d", &shelf, &pages);
            nobookarr[shelf] += 1; 
            shelarr[shelf] = (int*)realloc(shelarr[shelf], nobookarr[shelf] * sizeof(int));
            shelarr[shelf][nobookarr[shelf] - 1] = pages;
        } else if (type_of_query == 2) {
            int shelf, book;
            printf("Enter shelf index and book index: ");
            scanf("%d %d", &shelf, &book);
            if (shelf < noshel && book < nobookarr[shelf]) {
                printf("Number of pages: %d\n", shelarr[shelf][book]);
            } else {
                printf("Invalid shelf or book index!\n");
            }
        } else if (type_of_query == 3) {
            int shelf;
            printf("Enter shelf index: ");
            scanf("%d", &shelf);
            if (shelf < noshel) {
                printf("Number of books on shelf %d: %d\n", shelf, nobookarr[shelf]);
            } else {
                printf("Invalid shelf index!\n");
            }
        } else {
            printf("Invalid query type!\n");
        }
    }
    for (int i = 0; i < noshel; i++) {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);
    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/d5a9bb7d-e252-4c92-949f-dd3151f8834c)



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```python
#include <stdio.h>
int main() {
    int n, i, sum = 0;
    printf("Enter the number of integers: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("Sum of the integers in the array: %d\n", sum);
    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/56994403-1158-439b-bd2c-c9b92f2d12d6)

 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE

Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```python
#include <stdio.h>
#include <ctype.h> 
int main() {
    char sentence[1000];
    int i = 0, words = 0;
    int inWord = 0; 
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);
    while (sentence[i] != '\0') {
        if (!isspace(sentence[i]) && inWord == 0) {
            inWord = 1;
            words++;
        } else if (isspace(sentence[i])) {
            inWord = 0;
        }
        i++;
    }
    printf("The number of words in the sentence: %d\n", words);
    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/9c861dd2-e52c-4acc-bccf-6e7e3475e630)



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
