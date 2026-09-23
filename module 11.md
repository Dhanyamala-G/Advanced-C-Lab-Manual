# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include<stdio.h>
int max_of_four(int a,int b,int c,int d)
{
if(a>b && a>c && a>d)
{
return a;
}
else if(b>a && b>c && b>d)
{
return b;
}
else if(c>a && c>b && c>d)
{
return c;
}
else
{
return d;
}
}

int main()
{
int n1,n2,n3,n4,greater; 
scanf("%d%d%d%d",&n1,&n2,&n3,&n4); 
greater=max_of_four(n1,n2,n3,n4); 
printf("Greatest number is: %d",greater);
}
```
Output:<br>

<img width="257" height="100" alt="image" src="https://github.com/user-attachments/assets/346a1cb3-e796-471d-b239-1f769cd2a975" />

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
# EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
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
```
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

// 1. Define a function calculate_the_max that takes two integers n and k as parameters.
void calculate_the_max(int n, int k) {
    // 2. Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations.
    int max_and = 0;
    int max_or = 0;
    int max_xor = 0;

    // 3. Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            
            // 4. Check conditions and update maximum values that are strictly less than k.
            int current_and = i & j;
            int current_or  = i | j;
            int current_xor = i ^ j;

            if (current_and < k && current_and > max_and) {
                max_and = current_and;
            }
            if (current_or < k && current_or > max_or) {
                max_or = current_or;
            }
            if (current_xor < k && current_xor > max_xor) {
                max_xor = current_xor;
            }
        }
    }

    // Print the calculated maximum values
    printf("%d\n", max_and);
    printf("%d\n", max_or);
    printf("%d\n", max_xor);
}

int main() {
    // 5. Declare variables n and k to store user input.
    int n, k;
  
    // 6. Use scanf to take two integers as input.
    scanf("%d %d", &n, &k);
    
    // 7. Call the calculate_the_max function with input values.
    calculate_the_max(n, k);
 
    return 0;
}
```
Output:<br>
<img width="260" height="137" alt="image" src="https://github.com/user-attachments/assets/78cddb3f-5e18-46ec-b311-2c9f38eb680e" />

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    // 1. Declare variables noshel and noque
    int noshel, noque;

    // 2. Use scanf to take two integers as input
    if (scanf("%d %d", &noshel, &noque) != 2) {
        return 1;
    }

    // 3. Declare a 2D array shelarr and a 1D array nobookarr dynamically
    int* nobookarr = (int*)calloc(noshel, sizeof(int));
    int** shelarr = (int**)malloc(noshel * sizeof(int*));
    
    for (int i = 0; i < noshel; i++) {
        shelarr[i] = NULL;
    }

    // 4. Declare variables k and c to keep track of query indices/values
    int k, c;

    // 5. Use a for loop to iterate over the queries
    for (int q = 0; q < noque; q++) {
        int type;
        if (scanf("%d", &type) != 1) break;

        if (type == 1) {
            // Request Type 1: Insert a book with 'c' pages at the end of shelf 'k'
            scanf("%d %d", &k, &c);
            nobookarr[k]++;
            shelarr[k] = (int*)realloc(shelarr[k], nobookarr[k] * sizeof(int));
            shelarr[k][nobookarr[k] - 1] = c;
            
        } else if (type == 2) {
            // Request Type 2: Print the number of pages in the c-th book on the k-th shelf
            scanf("%d %d", &k, &c);
            printf("%d\n", shelarr[k][c]);
            
        } else if (type == 3) {
            // Request Type 3: Print the total number of books on the k-th shelf
            scanf("%d", &k);
            printf("%d\n", nobookarr[k]);
        }
    }

    // Free dynamically allocated memory to avoid leaks
    for (int i = 0; i < noshel; i++) {
        if (shelarr[i] != NULL) {
            free(shelarr[i]);
        }
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}
```
Output:<br>
<img width="326" height="253" alt="image" src="https://github.com/user-attachments/assets/a2ea8250-c9d8-403f-907f-853067c51c2e" />


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
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
```
#include <stdio.h>

int main() {
    // 1. Declare a variable n to store the number of integers.
    int n;

    // 2. Use scanf to take an integer n as input.
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // 3. Declare an array a of size n to store the integers.
    int a[n];

    // 4. Declare a variable sum and initialize it to zero.
    int sum = 0;

    // 5. Use a for loop to iterate n times.
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        // 6. Use scanf to input each integer and add it to the sum.
        scanf("%d", &a[i]);
        sum += a[i];
    }

    // 7. Print the final sum using printf.
    printf("Sum of the integers in the array = %d\n", sum);

    return 0;
}
```
Output:<br>
<img width="316" height="145" alt="image" src="https://github.com/user-attachments/assets/b405140e-6116-4d85-9d07-d6451baf8710" />

 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE



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
```
#include <stdio.h>

int main() {
    char sentence[1000];
    int i = 0;
    int word_count = 0;
    int in_word = 0; // Flag to track if we are inside a word (1) or not (0)

    // 1. Input the sentence
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // 2 & 3. Process each character of the sentence
    while (sentence[i] != '\0') {
        // Check if the current character is a space, tab, or newline
        if (sentence[i] == ' ' || sentence[i] == '\t' || sentence[i] == '\n') {
            in_word = 0; // We are now in a space between words
        } 
        // If it's the first non-space character after a space or at the start
        else if (in_word == 0) {
            in_word = 1;  // Mark that we have entered a word
            word_count++; // 3. Increment the word count
        }
        i++; // Move to the next character
    }

    // 5. Display the result
    printf("Total number of words = %d\n", word_count);

    return 0;
}
```
Output:<br>

<img width="317" height="112" alt="image" src="https://github.com/user-attachments/assets/8dbfceec-e4fd-4905-9635-04334654452c" />



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
