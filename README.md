Dynamic Knapsack

This function, dynamic_knapsack, is an implementation of the knapsack problem using dynamic programming. It calculates the maximum value that can be obtained by selecting items with specific weights and values, given a weight capacity.

The function takes three arguments:

    weight_cap: An integer representing the weight capacity of the knapsack.
    weights: A list of integers representing the weights of the items.
    values: A list of integers representing the values of the items.

This function was created as part of a lesson on Codecademy that teaches about dynamic programming. It demonstrates how dynamic programming can be used to efficiently solve the knapsack problem.
Algorithm

    The function starts by initializing the dimensions of a 2D matrix matrix with rows and cols. The number of rows is equal to the length of the weights list plus 1, and the number of columns is equal to weight_cap plus 1.

    The matrix is then initialized with -1 values. Each row is represented by a list.

    The function iterates through each row of the matrix using the variable index.

    For each row, the columns are initialized with -1 values using another iteration through the range of cols.

    The function then iterates through each column using the variable weight.

    Inside the column iteration, the function performs the following steps:
        If the current row (index) is 0 or the current column (weight) is 0, it means there are no items or no capacity available. In this case, the value in the matrix for that cell is set to 0.
        If the weight of the current item (weights[index-1]) is greater than the current column (weight), it means the current item cannot be included. In this case, the value in the matrix for that cell is set to the value of the cell above it in the previous row (matrix[index-1][weight]).
        Otherwise, the maximum value is calculated by comparing two options:
            The value of the cell above it in the previous row (matrix[index-1][weight]), representing not including the current item.
            The sum of the value of the current item and the value obtained by including the current item's weight (values[index-1]) and subtracting it from the current column (weight) in the previous row (matrix[index-1][weight - weights[index-1]]).
            The maximum of these two values is stored in the matrix for the current cell.

    Finally, the function returns the value in the bottom right cell of the matrix, which represents the maximum value that can be obtained with the given weight capacity.

Example Usage

python

weight_cap = 50
weights = [31, 10, 20, 19, 4, 3, 6]
values = [70, 20, 39, 37, 7, 5, 10]
print(dynamic_knapsack(weight_cap, weights, values))

This example calculates the maximum value that can be obtained by selecting items with weights [31, 10, 20, 19, 4, 3, 6] and values [70, 20, 39, 37, 7, 5, 10], given a weight capacity of 50. The result is then printed to the console.
