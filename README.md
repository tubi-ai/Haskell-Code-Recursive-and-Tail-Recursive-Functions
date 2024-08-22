Objective:
This Haskell code demonstrates the use of recursive and tail-recursive functions to perform operations on lists and integers. The code is organized into three main parts: incrementing elements of a list, extracting digits from an integer, and filtering list elements based on divisibility.

Part 1: Incrementing List Elements
Function: listIncr1
Type Signature: listIncr1 :: [Integer] -> [Integer]
Purpose: This function increments each element of a list of integers by 1.
Implementation:
The function uses recursion to traverse the list. For each element x in the list, x + 1 is computed, and the result is concatenated (++) with the recursively processed remainder of the list (xs).
Base Case: When the list is empty ([]), the function returns an empty list.
Recursive Case: When the list is non-empty, the head x is incremented by 1, and the function recursively processes the tail xs.
Example:
Input: [2, 1, 7, 6, 3, 8, 4]
Output: [3, 2, 8, 7, 4, 9, 5]


Part 2: Extracting Digits from an Integer
Function 1: digitsList (Recursive Version)
Type Signature: digitsList :: Integer -> [Integer]
Purpose: This function extracts the digits of a positive integer and returns them as a list.
Implementation:
The function recursively divides the integer by 10, appending the remainder (mod n 10) to the resulting list of digits.
Base Case 1: If n <= 0, an empty list is returned (to handle negative numbers or zero).
Base Case 2: If n < 10, the list contains the single digit n.
Recursive Case: The function continues dividing the number by 10 until all digits are processed.
Function 2: digitsListTail (Tail-Recursive Version)
Type Signature: digitsListTail :: Integer -> [Integer]
Purpose: This is a tail-recursive version of digitsList, which is optimized for better performance in Haskell by avoiding stack overflows on large inputs.
Implementation:
The function uses a helper function digitsListTailHelper with an accumulator (acc) to collect the digits in reverse order.
The base case and recursive case logic are similar to digitsList, but the accumulator is used to build the final list efficiently.
Example:
Input: 2705
Output: [2, 7, 0, 5]


Part 3: Filtering List Elements by Divisibility
Function: listDiv
Type Signature: listDiv :: [Integer] -> Integer -> [Integer]
Purpose: This function filters the elements of a list, returning only those that are divisible by a specified divisor.
Implementation:
The function recursively checks each element of the list to see if it is divisible by the given divisor using the modulo operation (mod x divisor == 0).
Base Case: If the list is empty, an empty list is returned.
Recursive Case: If an element x is divisible by the divisor, it is included in the result list; otherwise, the function continues with the next element.
Example:
Input: [24, 25, ..., 44], Divisor: 7
Output: [28, 35, 42]


Main Function:
The main function is the entry point of the program, where the defined functions are tested with various inputs. It prints the results of each operation, allowing for easy verification of correctness.
Conclusion:
This Haskell code effectively demonstrates the use of both standard recursion and tail recursion to perform operations on lists and integers. By structuring the code into distinct parts, it provides clear examples of common functional programming techniques in Haskell, emphasizing the importance of recursion and the efficiency benefits of tail recursion. The code is also well-suited for educational purposes, showing the progression from simple list manipulation to more complex tasks like digit extraction and filtering.
