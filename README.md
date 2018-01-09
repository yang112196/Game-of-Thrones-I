# Game-of-Thrones-I
palindrome permutation
Question from heckerrank.com (week of coding)

Input Format
  A single line which contains the input string.

Constraints
  1 <= length of string <= 100000 
  Each character of the string is a lowercase English letter.
  
Output Format
  A single line which contains YES or NO in uppercase.
  
Solution:
    Find the number of times that different letters from the first to the end are repeated. There are two different cases. First, if the length of the string is even: you just need to ensure that the times for each different letter are all even. Second, if the length of the string is odd: you need to ensure that there's only one letter is repeated in odd times and other letters are repeated in even times.

    import java.io.*;
    import java.util.*;
    import java.text.*;
    import java.math.*;
    import java.util.regex.*;
    
    
    public class Solution {

      public static String gameOfThrones(String s){
        String result = "";                                //results either "YES" or "NO"
        String temp = s;                                   //temporary String to save the modified String "s"
        ArrayList<Integer> letter = new ArrayList<>();     //to save different letter's repeated times
        int numberOfIter = 1;
        int count = 0;
        
        if(s.length() <= 100000 && s.length() >= 1) {
        		for(int i = 0; i<temp.length(); ++i){         //find the number of the times of repeated letter
                if(temp.charAt(i) != ' ') {

            			for(int j = i + 1; j<temp.length(); ++j){
            				if(temp.charAt(j) != ' ' ) {
            					if(temp.charAt(i) == temp.charAt(j)){
            						numberOfIter++;
                            
            					}
            				}
            				else {
            					continue;
            				}
                    
                    
            			}
                System.out.println("index: " + i + " num: " + numberOfIter);
                letter.add(numberOfIter);
                temp = temp.replace(s.charAt(i), ' ');
                numberOfIter = 1;

                }     
            }
            
            for(int i = 0; i<letter.size(); ++i){          //using for loop and if-else statement to tell 

                  
                  if(s.length() % 2 == 0){
                    
                    if(letter.get(i) % 2 == 0){
                        result = "YES";
                    }
                    else{
                        result = "NO";
                        break;
                    }
                    
                }
                else{
                    if(letter.get(i) % 2 != 0){
                        count++;
                    }
                    if(count >1){
                        result = "NO";
                    }
                    else{
                        result = "YES";
                    }
                }   
            }
        }

        
        return result;
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        String s = in.next();
        String result = gameOfThrones(s);
        System.out.println(result);
    }
    }
