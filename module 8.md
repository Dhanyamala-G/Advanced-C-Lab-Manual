# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
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
```
#include<stdio.h> 
#include<math.h> 
int main()
{
int n; 
scanf("%d",&n);
switch(n)
{
case 71:
{printf("seventy one"); 
break;}

case 72:
{
printf("seventy two"); 
break;
}
case 73:
{
printf("seventy three"); 
break;
}
case 74:
{
printf("seventy four"); 
break;
}
case 75:
{
printf("seventy five"); 
break;
}
case 76:
{
printf("seventy six"); 
break;
}
case 77:
{
printf("seventy seven"); 
break;
}
 
case 78:
{
printf("seventy eight"); 
break;
}
case 79:
{
printf("seventy nine"); 
break;
}
default:
{
printf("Greater than 79");
}
}
}
```






Output:


<img width="251" height="97" alt="image" src="https://github.com/user-attachments/assets/f18b5e3d-deaa-4110-a126-ef2bd30a03e1" />






Result:
Thus, the program is verified successfully
 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
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

```
#include<stdio.h> 
#include<string.h> 
int main()
{
char a[50]; 
scanf("%s",a); 
int l=strlen(a); 
char h='0';
for(int i=0;i<4;i++)
{
    int c=0;
    for(int j=0;j<l;j++)
    {
        if(a[j]==h)
        {
            c+=1;
        }
    }
    printf("%d ",c); h++;
}
}


```



Output:


<img width="261" height="95" alt="image" src="https://github.com/user-attachments/assets/2e40cf10-80ab-415b-94d1-567a4b6c57e9" />






Result:
Thus, the program is verified successfully

# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
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

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Helper function to swap two string pointers
void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

// Helper function to reverse an array of strings from index 'start' to 'end'
void reverse(char **s, int start, int end) {
    while (start < end) {
        swap(&s[start], &s[end]);
        start++;
        end--;
    }
}

// Function to find the next lexicographical permutation
int next_permutation(char **s, int n) {
    // 1. Find the largest index i such that s[i] < s[i+1]
    int i = n - 2;
    while (i >= 0 && strcmp(s[i], s[i + 1]) >= 0) {
        i--;
    }
    
    // If no such index exists, we have reached the last permutation
    if (i < 0) {
        return 0;
    }
    
    // 2. Find the largest index j greater than i such that s[i] < s[j]
    int j = n - 1;
    while (strcmp(s[i], s[j]) >= 0) {
        j--;
    }
    
    // 3. Swap s[i] and s[j]
    swap(&s[i], &s[j]);
    
    // 4. Reverse the elements from index i + 1 to the end
    reverse(s, i + 1, n - 1);
    
    return 1;
}

// Comparison function for qsort to sort the initial input alphabetically
int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

int main() {
    // Step 2: Declare variables s (pointer to array of strings) and n (number of strings)
    char **s;
    int n;
    
    // Step 4: Input number of strings n from the user
    printf("Enter the number of strings: ");
    if (scanf("%d", &n) != 1 || n <= 0) {
        return 1;
    }
    
    // Step 3: Dynamically allocate memory for s to store an array of string pointers
    s = (char **)malloc(n * sizeof(char *));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    
    // Step 4 (continued): Dynamically allocate memory for each string in s and read inputs
    printf("Enter %d strings:\n", n);
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char)); // Allocating 100 bytes per string
        if (s[i] == NULL) {
            printf("Memory allocation failed.\n");
            return 1;
        }
        scanf("%s", s[i]);
    }
    
    // Sort initial elements to ensure permutations start from the absolute lowest order
    qsort(s, n, sizeof(char *), compare);
    
    // Step 5: Permutation Generation Loop
    printf("\nAll permutations in strict lexicographical order:\n");
    do {
        for (int i = 0; i < n; i++) {
            printf("%s%c", s[i], (i == n - 1) ? '\n' : ' ');
        }
    } while (next_permutation(s, n));
    
    // Step 6: Memory Deallocation
    for (int i = 0; i < n; i++) {
        free(s[i]); // Free the memory allocated for each string
    }
    free(s); // Free the memory allocated for s
    
    // Step 7: End
    return 0;
}
```



Output:


<img width="437" height="287" alt="image" src="https://github.com/user-attachments/assets/9183e357-637c-492b-a5dc-b3cfdeba5a00" />






Result:
Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
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

```
#include <stdio.h>

int main() {
    int n, i, j, min, len;

    // 3. Read the value of n from the user
    printf("Enter the value of n: ");
    if (scanf("%d", &n) != 1) {
        return 1;
    }

    // 4. Calculate the length of the side of the square matrix
    len = n * 2 - 1;

    // 5. Matrix Generation Loop
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            
            // 6. Calculate min as the minimum distance to the 4 borders
            // Distances: Top = i, Bottom = (len-1) - i, Left = j, Right = (len-1) - j
            
            int dist_top = i;
            int dist_bottom = len - 1 - i;
            int dist_left = j;
            int dist_right = len - 1 - j;

            // Find the minimum among the four distances
            min = dist_top;
            if (dist_bottom < min) min = dist_bottom;
            if (dist_left < min)   min = dist_left;
            if (dist_right < min)  min = dist_right;

            // Print the value based on the pattern type:
            // Type A (Outermost layer is n, center is 1):
            printf("%d ", n - min);
            
            // Note: If your pattern has 1 on the outside and n in the center, 
            // use: printf("%d ", min + 1);
        }
        printf("\n"); // Newline after each row
    }

    return 0;
}
```



Output:


<img width="273" height="277" alt="image" src="https://github.com/user-attachments/assets/58066714-c2b7-40e3-9d8d-17cc9697dbae" />






Result:
Thus, the program is verified successfully

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

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

```
#include <stdio.h>

// Function prototype
int square();

int main() {
    int result;

    // Call the square() function and display the result
    result = square();
    printf("The square of the number is: %d\n", result);

    return 0;
}

// Function definition: Takes no arguments, returns an integer
int square() {
    int num, squared_value;

    // Ask the user to input a number
    printf("Enter an integer: ");
    scanf("%d", &num);

    // Calculate the square of the number
    squared_value = num * num;

    // Return the squared value
    return squared_value;
}
```



Output:


<img width="297" height="102" alt="image" src="https://github.com/user-attachments/assets/9d360fca-92db-4970-b9cd-2ad28fc8e771" />






Result:
Thus, the program is verified successfully



























