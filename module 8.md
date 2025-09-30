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
```c
#include <stdio.h>

int main() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n) {
        case 71:
            printf("seventy one\n");
            break;
        case 72:
            printf("seventy two\n");
            break;
        case 73:
            printf("seventy three\n");
            break;
        case 74:
            printf("seventy four\n");
            break;
        case 75:
            printf("seventy five\n");
            break;
        case 76:
            printf("seventy six\n");
            break;
        case 77:
            printf("seventy seven\n");
            break;
        case 78:
            printf("seventy eight\n");
            break;
        case 79:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
            break;
    }

    return 0;
}
```

Output:


<img width="567" height="267" alt="image" src="https://github.com/user-attachments/assets/5e96b7ec-69bc-4f6c-ab3f-f4b446cab7e7" />





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
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    int freq[10]={0};
    char str[100];
    scanf("%s",str);
    for(int i=0;i<strlen(str);i++){
        if(isdigit(str[i])){
            freq[str[i] - '0']++;
        }
    }
    for(int i=0;i<10;i++){
        printf("%d ",freq[i]);
    }return 0;
}
```



Output

<img width="550" height="136" alt="image" src="https://github.com/user-attachments/assets/53ea20de-7ac0-452c-bfb0-fbd06b48d35b" />






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
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
 #define MAX 10
 #define LEN 100
 void swap(char arr[MAX][LEN],int i,int j){
     char temp[LEN];
     strcpy(temp,arr[i]);
     strcpy(arr[i],arr[j]);
     strcpy(arr[j],temp);
}
int next_permutation(char arr[MAX][LEN],int n){
    int i=n-2;
    while(i>=0 &&strcmp(arr[i],arr[i+1])>=0) i--;
    if(i<0) return 0;
    int j=n-1;
    while(strcmp(arr[i],arr[i+1])>=0) j--;
    swap(arr,i,j);
    int left=i+1,right=n-1;
    while(left<right) swap(arr,left++,right--);
    return 1;
}
int cmp(const void *a,const void *b){
    return strcmp((char *)a,(char *)b);
}
int main(){
    int n;
    scanf("%d",&n);
    char arr[MAX][LEN];
    for(int i=0;i<n;i++) scanf("%s",arr[i]);
    qsort(arr,n,LEN,cmp);
    do{
        for(int i=0;i<n;i++) printf("%s ",arr[i]);
        printf("\n");
    }while(next_permutation(arr,n));
    return 0;
}
```

Output:

<img width="334" height="296" alt="image" src="https://github.com/user-attachments/assets/19d69f2a-9f23-4807-865d-7790f87cc5e7" />




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
```c
#include<stdio.h>
int main()
{
    int n,len,min,i,j;
    scanf("%d",&n);
    len=2*n-1;
    for(i=0;i<len;i++)
    {
        for(j=0;j<len;j++)
        {
            if(i<j)
            min=i;
            else
            min=j;
            if(min>=len-i-1)
            min=len-i-1;
            if(min>=len-j-1)
            min=len-j-1;
            printf("%d ",n-min);
        }
        printf("\n");
    }
}
```



Output:

<img width="520" height="578" alt="image" src="https://github.com/user-attachments/assets/f37cf057-f85b-4591-89dd-8403e41c0885" />






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
```c
#include <stdio.h>

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result = square();
    printf("The square of the number is: %d\n", result);
    return 0;
}
```


Output:

<img width="1136" height="361" alt="image" src="https://github.com/user-attachments/assets/29312988-4142-4bcc-8bd9-5270804ebb35" />





Result:
Thus, the program is verified successfully
