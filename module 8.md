## EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
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
#include <stdio.h>

int main() {
    int n;

    // Input
    scanf("%d", &n);

    // Switch statement
    switch (n) {
        case 5:  printf("seventy one"); break;
        case 6:  printf("seventy two"); break;
        case 7:  printf("seventy three"); break;
        case 8:  printf("seventy four"); break;
        case 9:  printf("seventy five"); break;
        case 10: printf("seventy six"); break;
        case 11: printf("seventy seven"); break;
        case 12: printf("seventy eight"); break;
        case 13: printf("seventy nine"); break;
        default: printf("greater than 13");
    }

    return 0;
}
```






Output:


<img width="524" height="253" alt="image" src="https://github.com/user-attachments/assets/1baebb76-c404-4141-89da-c08a9bbe7a5f" />







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

```
#include <stdio.h>

int main() {
    char a[50];
    int c, h;

    // Input string
    scanf("%s", a);

    // Outer loop for digits 0 to 3
    for (h = 0; h <= 3; h++) {
        c = 0;

        // Count frequency of current digit
        for (int i = 0; a[i] != '\0'; i++) {
            if (a[i] == (h + '0')) {
                c++;
            }
        }

        // Print count followed by space
        printf("%d ", c);
    }

    return 0;
}
```





Output:


<img width="469" height="329" alt="image" src="https://github.com/user-attachments/assets/e198da59-c723-437b-90f5-b5cf80793a7c" />







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

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void swap(char *a, char *b) {
    char t = *a;
    *a = *b;
    *b = t;
}

int next_permutation(char *s, int n) {
    int i = n - 2;

    while (i >= 0 && s[i] >= s[i + 1])
        i--;

    if (i < 0)
        return 0;

    int j = n - 1;
    while (s[j] <= s[i])
        j--;

    swap(&s[i], &s[j]);

    int l = i + 1, r = n - 1;
    while (l < r) {
        swap(&s[l], &s[r]);
        l++;
        r--;
    }

    return 1;
}

int main() {
    int n;
    char *s;

    scanf("%d", &n);
    s = (char *)malloc((n + 1) * sizeof(char));
    scanf("%s", s);

    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (s[i] > s[j]) {
                swap(&s[i], &s[j]);
            }
        }
    }

    do {
        printf("%s\n", s);
    } while (next_permutation(s, n));

    free(s);
    return 0;
}
```




Output:


<img width="504" height="376" alt="image" src="https://github.com/user-attachments/assets/12c7c3a3-94a0-4db4-bfc0-ab4c4f2607fb" />







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

```
#include <stdio.h>

int main() {
    int n, i, j, min;
    int len;

    scanf("%d", &n);

    len = n * 2 - 1;

    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            min = i;
            if (j < min) min = j;
            if (len - i - 1 < min) min = len - i - 1;
            if (len - j - 1 < min) min = len - j - 1;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```




Output:


<img width="465" height="315" alt="image" src="https://github.com/user-attachments/assets/7f84fe52-57d1-42e9-b378-fcf023cbf8b9" />







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

```
#include <stdio.h>

int square() {
    int num;
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    result = square();
    printf("%d", result);
    return 0;
}
```




Output:


<img width="516" height="194" alt="image" src="https://github.com/user-attachments/assets/efc43648-5d0f-494c-be34-cf1dddbb5a6e" />







Result:
Thus, the program is verified successfully



























