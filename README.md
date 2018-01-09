# Game-of-Thrones-I
palindrome permutation
Question from heckerrank.com (week of coding)

Input Format:
  A single line which contains the input string.

Constraints:
  1 <= length of string <= 100000 
  Each character of the string is a lowercase English letter.
  
Output Format:
  A single line which contains YES or NO in uppercase.
  
Solution:
    Find the number of times that different letters from the first to the end are repeated. There are two different cases. First, if the length of the string is even: you just need to ensure that the times for each different letter are all even. Second, if the length of the string is odd: you need to ensure that there's only one letter is repeated in odd times and other letters are repeated in even times.
