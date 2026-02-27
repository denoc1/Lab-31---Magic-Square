# Lab-31---Magic-Square

## Description

A **magic square** is a two-dimensional array of integers with the same number of rows as columns (i.e., an `n x n` array). To qualify as a magic square, the array must satisfy the following conditions:

- The sum of the numbers in each **row**, each **column**, and both **main diagonals** is the same.
- This value is called the **magic number**.

---

### Examples of Magic Squares (3x3)

      8  1  6
      3  5  7
      4  9  2


      13   6  11
       8  10  12
       9  14   7

###  Example of a Magic Square (4 x 4)

      16   2   3  13
      5   11  10  8
      9   7    6  12
      4   14  15   1

###  Example of a Magic Square (5 x 5)

     17  24   1   8  15
     23   5   7  14  16
      4   6  13  20  22
     10  12  19  21   3
     11  18  25   2   9


### Examples of Non-Magic Square

      2  7  6
      9  5  1
      4  3  8


      3  7  6
      8  5  4
      2  9  1

---

## Part 1 – Basic Lab Requirement

Write a class `MagicSquare` with the following **instance variable** and **methods**. Documentation is included for instruction and for you to use.

```java
public class MagicSquare {
    private int[][] mat;

    /**
     * Constructs a MagicSquare object using a provided 2D array.
     *
     * @param mat a two-dimensional array representing the square matrix.
     * Precondition: The input matrix must be square (n x n).
     * Postcondition: Initializes the MagicSquare object with the given matrix.
     */
    public MagicSquare(int[][] mat) {
        // Implementation
    }

    /**
     * returns the matrix in a String formatted manner.
     *
     * Precondition: The matrix (mat) has been initialized and is not null.
     * Postcondition: Returns the matrix in a String format to be printed when called.
     */
    public String toString() {
        // Implementation
    }

    /**
     * Computes the sum of the elements in the given row.
     *
     * @param row the index of the row to sum (0-based).
     * Precondition: The matrix (mat) has been initialized and 0 <= row < mat.length.
     * Postcondition: Returns the sum of the elements in the specified row.
     */
    public int sumRow(int row) {
        // Implementation
    }

    /**
     * Computes the sum of the elements in the given column.
     *
     * @param col the index of the column to sum (0-based).
     * Precondition: The matrix (mat) has been initialized and 0 <= col < mat[0].length.
     * Postcondition: Returns the sum of the elements in the specified column.
     */
    public int sumCol(int col) {
        // Implementation
    }

    /**
     * Computes the sum of the elements in the major diagonal (top-left to bottom-right).
     *
     * Precondition: The matrix (mat) is square and has been initialized.
     * Postcondition: Returns the sum of the elements in the major diagonal.
     */
    public int sumMajorDiag() {
        // Implementation
    }

    /**
     * Computes the sum of the elements in the minor diagonal (top-right to bottom-left).
     *
     * Precondition: The matrix (mat) is square and has been initialized.
     * Postcondition: Returns the sum of the elements in the minor diagonal.
     */
    public int sumMinorDiag() {
        // Implementation
    }

    /**
     * Checks if the matrix is a magic square.
     * This method should call the previous methods appropriately.
     *
     * Precondition: The matrix (mat) is square and has been initialized.
     * Postcondition: Returns true if the matrix is a magic square; false otherwise.
     */
    public boolean isMagicSquare() {
        // Implementation
    }

    /**
     * Bonus opportunity – optional.
     *
     * Determines if the matrix is a "pure" magic square.
     *
     * A "pure" magic square has no duplicate values and contains only non-negative values.
     *
     * Precondition: The matrix (mat) has been initialized.
     * Postcondition: Returns true if the matrix is a "pure" magic square; false otherwise.
     */
    public boolean isPureMagicSquare() {
        // Implementation
    }
}
```

---

## Part 2 – Reading a Magic Square from a File

Many real-world programs read data from external files rather than hardcoding it.

In this part of the lab, you will **read a magic square from a file** and store it in a 2D array.

---

### File Format

- The first number in the file is the size `n` of the square  
- The next `n²` numbers represent the square values  
- Numbers can be separated by spaces or line breaks (whitespace)  
- You may assume the file exists and is correctly formatted

#### Example file (`magic.txt`)
```
3
8 1 6
3 5 7
4 9 2
```

---

### Method Requirement

Write a **static method** in the Lab31 class that reads the file and returns a 2D array.

```java
public static int[][] readSquare(String filename) throws FileNotFoundException
```

- Opens the file using a `Scanner`  
- Reads the size of the square  
- Creates a 2D array of the appropriate size  
- Fills the array with values from the file  
- Returns the completed 2D array

---

### Using Your Method

```java
int[][] data = readSquare("magic.txt");
MagicSquare ms = new MagicSquare(data);

System.out.println(ms);
System.out.println("Is magic square is " + ms.isMagicSquare());
```

---

### Important Notes

- The `MagicSquare` class should **not** read the file directly  
- You may assume the file contains correct data  
- You do **not** need to handle exceptions beyond adding `throws FileNotFoundException`  

---

## Optional Extension - write the isPureMagicSquare() method that determines if a magic square is pure (no duplicate values and
only non-negative values).

   /**
     *  This is a Bonus opportunity - it is not required!
     *
     * Determines if the matrix is a "pure" magic square.
     * 
     * A "pure" magic square has no duplicate values and contains only non-negative values.
     * 
     * Precondition: The matrix (mat) has been initialized.
     * Postcondition: Returns true if the matrix is a "pure" magic square; false otherwise.
     */
    public boolean isPureMagicSquare() {
        // Implementation
    }
}


---

## Examples of Non-Pure Magic Squares
```
2  2  2
2  2  2
2  2  2
```

```
-1  4  3
6   2 -2
1   0  5
```

> A "pure" magic square contains only unique, non-negative values.

---

## Submission Guidelines

- Submit your `MagicSquare.java` file  
- Include any test files used  
- Ensure your code compiles and runs correctly  
- Comment your code where appropriate
