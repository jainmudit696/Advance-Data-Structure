Problem Statement:  1) Write a program to read an integer 1D array containing 8 bits (0s, 1s) of an unsigned binary integer. The program should print the decimal value for the integer
   
Algorithm: 
1. Start
2. Declare an integer array to store binary digits.
3. Display and take user input for an 8 bit binary number, storing each digit in the array.
4. Initialize a variable for decimal value 0.
5. Use a loop to iterate over each position in the array.
6. Multiply the binary digit at current position by 2 raised to the power of (8 - current position)
7. Add the result to the decimal value.
8. Display the calculated decimal value.
9. End
 
Source Code:

#include <stdio.h>

int main() {
    int Array[8];
    printf("Write the binary number:\n");
    for (int i = 0; i < 8; i++) {
        printf("Binary Number %d: ", i + 1);
        scanf("%d", &Array[i]);
    }
    int decimalValue = 0;
    for (int i = 0; i < 8; i++) {
        decimalValue += Array[i] * (1 << (7 - i));
    }
    printf("Decimal value: %d\n", decimalValue);
    return 0;
}


Problem Statement:  2)   Currency notes are available in the following seven denominations: Rs. 1, Rs. 2, Rs. 5, Rs. 10, Rs. 20, Rs.50, and Rs. 100.
You will first read an integer array (named purse [7]) of seven elements, where the array elements represent the number of notes of each denomination (in increasing order of denomination) available with you. You are also given an amount of money to be paid using these notes. The amount will be less than Rs. 1000. You have to pay the amount using minimum number of notes. Print the number of notes of each denomination which you will use to pay the amount. If the amount cannot be paid using the available notes, print “Failed to Pay”.

Algorithm: 
1.	Start
2.	Initialize arrays 'wallet’ and 'denominations'.
3.	Take user’s input for each denominations in wallet.
4.	Input amount to be paid (>1000) and store it in 'amount'.
5.	Call MinimumNotes(wallet, amount, denominations).
6.	Function MinimumNotes(wallet, amount, denominations):
7.	Initialize array 'notesUsed'.
8.	Iterate in reverse through 'denominations'.
9.	Calculate notes to use (minimum of amount/denomination and quantity in 'wallet').
10.	Update 'amount' and 'wallet’ based on notes used.
11.	Store notes used in 'notesUsed'.
12.	Check if amount is zero.
13.	If yes, print "Smallest amount of notes taken:".
14.	Iterate through 'notesUsed' and print denomination and notes used.
15.	If no, print "Failed to Pay".
16.	End

Source Code:  

#include <stdio.h>

void MinimumNotes(int wallet[], int amount, int notesUsed[], int denominations[], int denominationsSize) {
    for (int i = denominationsSize - 1; i >= 0 && amount > 0; i--) {
        int denomination = denominations[i];
        int notesToUse = (amount / denomination) < wallet[i] ? (amount / denomination) : wallet[i];
        amount -= notesToUse * denomination;
        wallet[i] -= notesToUse;
        notesUsed[i] = notesToUse;
    }
    if (amount == 0) {
        printf("Smallest amount of notes taken:\n");
        for (int i = 0; i < denominationsSize; i++) {
        if (notesUsed[i] > 0) {
                printf("Rs. %d: %d notes\n", denominations[i], notesUsed[i]); }  }
    } else {
        printf("Failed to Pay\n");
    }
}

int main() {
    int wallet[7];
    int notesUsed[7];
    int denominations[] = {1, 2, 5, 10, 20, 50, 100};
    int denominationsSize = sizeof(denominations) / sizeof(denominations[0]);
    for (int i = 0; i < denominationsSize; i++) {
        printf("Enter the required amount %d RS note: ", denominations[i]);
        scanf("%d", &wallet[i]);
    }
    printf("Enter amount to pay > 1000: ");
    int amount;
    scanf("%d", &amount);
    MinimumNotes(wallet, amount, notesUsed, denominations, denominationsSize);
    return 0;
}


Problem Statement: 3) Write functions to perform the following operations with two-dimensional arrays.
i) Reading any two-dimensional array elements.
ii) Finding maximum and standard deviation of array elements.
iii) Printing the transpose of a matrix

Algorithm: i) Reading any two-dimensional array elements:
1. Start
2. Initializing variables for rows & columns.
3. Display a messege to user to enter the no. of rows & columns.
4. Declaring a 2 dimentional array ‘array’ with max dimention[100][100].
5. Call the ‘readArray’ function to input value into the array.
6. Display the array using the ‘printArray’ function.
7.End

Algorithm for ii) Finding maximum and standard deviation of array elements.
1.	Start
2.	Initialize variable for row, column, array & result.
3.	Display a messege to user to enter the no. of rows & columns.
4.	Declaring a 2 dimentional array ‘array’ with max dimention[100][100].
5.	Call the ‘readArray’ function to input value into the array.
6.	Call the ‘MaxStd’ function to calculate the max value & standard deviation.
7.	Display the array using the ‘printArray’ function.
8.	Output the max value & standard deviation.
9.	End
    
Algorithm for iii) Printing the transpose of a matrix
1.	Start
2.	Initialize variable for row, column, & transpose.
3.	Display a messege to user to enter the no. of rows & columns.
4.	Declaring a 2 dimentional array ‘array’ with max dimention[100][100].
5.	Call the ‘readArray’ function to input value into the array.
6.	Call the transpose matrix function to compute the transpose
7.	Display the original array using the ‘printArray’ function.
8.	Display the transposed array using the ‘printArray’ function.
9.	End

Source Code:  

#include <stdio.h>
#include <math.h>

void printArray(int array[][100], int rows, int columns) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < columns; j++) {
            printf("%d ", array[i][j]);
        }
        printf("\n");
    }
}
int transposeMatrix(int matrix[][100], int rows, int columns, int transpose[][100]) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < columns; j++) {
            transpose[j][i] = matrix[i][j];
        }
    }
}
void readArray(int rows, int columns, int array[][100]) {
    printf("Enter the values:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < columns; j++) {
            scanf("%d", &array[i][j]);
        }
    }
}
void MaxStd(int array[][100], int rows, int columns, double result[]) {
    int max = -2147483648;  // INT_MIN
    double sum = 0, sumSquares = 0;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < columns; j++) {
            int element = array[i][j];
            max = (max > element) ? max : element;
            sum += element;
            sumSquares += element * element;
        }
    }
   double mean = sum / (rows * columns);
    double variance = (sumSquares / (rows * columns)) - (mean * mean);
    double stdDeviation = sqrt(variance);
    result[0] = max;
    result[1] = stdDeviation;
}

int main() {
    int rows, columns;
    printf("Enter Rows and Columns: ");
    scanf("%d %d", &rows, &columns);
    int array[100][100];
    readArray(rows, columns, array);
    printf("Array is:\n");
    printArray(array, rows, columns);
    double result[2];
    MaxStd(array, rows, columns, result);
    printf("Maximum value: %f\n", result[0]);
    printf("Standard Deviation: %f\n", result[1]);
    int transpose[100][100];
    transposeMatrix(array, rows, columns, transpose);
    printf("Transposed Array:\n");
    printArray(transpose, columns, rows);
    return 0;
}


