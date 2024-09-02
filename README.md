# Experiment-8
## AIM
To study and implement C++ 2D array matrices
## THEORY
Matrices in C++ are represented as 2D arrays. They are used to store and manipulate data in a structured, tabular form.

Introduction to Matrices
A matrix is a collection of elements arranged in rows and columns.
In C++, matrices are typically implemented using 2D arrays.

Declaring a Matrix
syntax for declaring a 2D array (matrix)
```
data_type matrix_name[rows][columns];
```
Initializing a Matrix
for eg
```
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```
Accessing Elements of a Matrix
Elements of a matrix are accessed using row and column indices.
For eg
```
int value = matrix[1][2];
```
Addition of matrices :
To add two matrices in C++, you can use a nested loop structure to iterate through each element of the matrices and add corresponding elements.
i) Matrix Size Input: The program asks for the number of rows and columns to define the size of the matrices.
ii) Matrix Elements Input: It then prompts the user to enter the elements for the two matrices.
iii) Matrix Addition: The program adds the corresponding elements of the two matrices.
iv) Output: Finally, it prints the result .

Subtraction of matrices
i) The program first asks the user to input the number of rows and columns for the matrices.
ii) It then prompts the user to input the elements for both matrices.
iii) The subtraction is performed by iterating through each element of the matrices and subtracting the corresponding elements.
iv) The resultant matrix is then printed on the screen.
## CODE AND OUTPUT
A : Entering elements of matrix
```
//To study and implement C++ 2D Array Matrices 
#include <iostream>
using namespace std;

int main() {
    int temp[3][3], i, j,k,l;
    for (i=0 ; i<3 ; i++){
        for (j=0;j<3;j++){
            cout<<" Enter element-("<<i<<j<<"):";
            cin>>temp[i][j];
        }
    }
    for(k-0; k<3; k++){
        for (l=0;l<3;l++){
            cout<<temp[k][l];
            cout<<" ";
    }
    cout <<endl;
    }
}
```
![81](https://github.com/user-attachments/assets/2abdb9b3-eb6c-4e3f-8573-953586e84f51)

 B : Addition and Subtraction of two matrices
 ```
// Addition and Subtraction of 2 Matrix

#include <iostream>
using namespace std;

int main() {
    int A[2][2], B[2][2], addition[2][2], subtraction[2][2];

    // Input values for matrix A
    cout << endl << "Enter values for 2-D array A: " << endl;
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            cin >> A[i][j];
        }
    }

    // Display values of matrix A
    cout << endl << "Values of 2-D array A: " << endl;
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            cout << A[i][j] << " ";
        }
        cout << endl; // This will print the second row in the second line
    }

    // Input values for matrix B
    cout << endl << "Enter values for 2-D array B: " << endl;
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            cin >> B[i][j];
        }
    }

    // Display values of matrix B
    cout << endl << "Values of 2-D array B: " << endl;
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            cout << B[i][j] << " ";
        }
        cout << endl; // This will print the second row in the second line
    }

    // Addition of matrices
    cout << "Value of Addition Array are: " << endl;
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            addition[i][j] = A[i][j] + B[i][j];
            cout << addition[i][j] << " ";
        }
        cout << endl; // This will print the second row in the second line
    }

    // Subtraction of matrices
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            subtraction[i][j] = A[i][j] - B[i][j];
        }
    }

    // Display subtraction result
    cout << endl << "Values of Subtraction Array are: " << endl;
    for(int i = 0; i < 2; i++) {
        for(int j = 0; j < 2; j++) {
            cout << subtraction[i][j] << " ";
        }
        cout << endl; // This will print the second row in the second line
    }

    return 0;
}
```
## Output :
![image](https://github.com/user-attachments/assets/e71356d5-8853-4a8f-8b2a-865115ab3773)

D : Multiplication of two matrices
```
// Matrix multiplication 
#include <iostream>
using namespace std;

int main() {
    int r1, c1, r2, c2;
    
    // Input dimensions of the first matrix
    cout << "Enter rows and columns for the first matrix: ";
    cin >> r1 >> c1;

    // Input dimensions of the second matrix
    cout << "Enter rows and columns for the second matrix: ";
    cin >> r2 >> c2;

    // Check if matrix multiplication is possible
    if (c1 != r2) {
        cout << "Matrix multiplication not possible!" << endl;
        return 0;
    }

    // Define the matrices
    int m1[r1][c1], m2[r2][c2], result[r1][c2];

    // Input elements of the first and second matrix
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    } 
    // Initialize the result matrix with zeros
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            result[i][j] = 0;
        }
    }

    // Matrix multiplication
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            for (int k = 0; k < c1; k++) {
                result[i][j] += m1[i][k] * m2[k][j];
            }
        }
    }

    // Display the result
    cout << "Resultant matrix:\n";
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            cout << result[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
![84](https://github.com/user-attachments/assets/3077d5c2-a0dc-468b-b4b7-00df88eacd46)

E : Transpose of a matrix
```
#include <iostream>
using namespace std;

int main() {
    int r, c ;

    // Getting the size of the matrix
    cout << "Enter the number of rows and columns of the matrix: ";
    cin >> r  >> c ;

    int m[r][c], transpose[c][r];

    // Getting elements of the matrix
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r; ++i) {
        for (int j = 0; j < c; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m[i][j];
        }
    }

    // Transposing the matrix
    for(int i = 0; i < r; ++i) {
        for(int j = 0; j < c; ++j) {
            transpose[j][i] = m[i][j];
        }
    }

    // Displaying the transpose of the matrix
    cout << "\nTranspose of the matrix:" << endl;
    for(int i = 0; i < c; ++i) {
        for(int j = 0; j < r; ++j) {
            cout << transpose[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
![85](https://github.com/user-attachments/assets/713fb4b3-b3b2-4197-87cf-bcf07a956cfc)

 F : Diagnol addition of a matrix
 ```
//DIAGONAL ADDITION 
#include <iostream>
using namespace std;


const int MAX = 100;

void printDiagonalSums(int mat[][MAX], int n) 
{ 
    int principal = 0;
    
    for (int i = 0; i < n; i++)  
    { 
        // Condition for principal diagonal 
        principal += mat[i][i]; 
    } 
  
    cout << "Sum of the diagonal elements is: " << principal << endl; 
} 

int main() 
{ 
    int a[][MAX] = {{1, 2, 3, 4},  
                    {5, 6, 7, 8},  
                    {1, 2, 3, 4},  
                    {5, 6, 7, 8}}; 
    printDiagonalSums(a, 4); 
return 0;
}
```
![86](https://github.com/user-attachments/assets/aa04f190-b6f0-4f58-8c37-f7e526038bf5)

## CONCLUSION
This experiment provides valuable insight into fundamental concepts in programming, particularly in handling data structures that require multi-dimensional organization. Through this process, we gain a deeper understanding of how to:

1.Efficiently Store and Manipulate Data: Using 2D arrays, we can efficiently store data in a tabular format, making it easier to perform operations like addition, subtraction, and multiplication of matrices.

2.Develop Problem-Solving Skills: Implementing matrix operations enhances logical thinking and problem-solving skills, as it requires careful consideration of indices, loops, and data handling.

3.Understand Memory Management: Working with 2D arrays in C++ also provides an understanding of how memory is allocated and accessed in programming, especially in managing rows and columns of data.

4.Apply Concepts in Real-World Scenarios: Matrix operations are fundamental in various fields such as engineering, computer graphics, machine learning, and scientific computing. Understanding how to implement these in C++ prepares us to tackle more complex problems in these domains.





