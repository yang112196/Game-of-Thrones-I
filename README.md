# Game-of-Thrones-I
palindrome permutation


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
//                System.out.println(temp);
                 numberOfIter = 1;

                }     
            }
            
            for(int i = 0; i<letter.size(); ++i){          //using for loop and if-else statement to tell 
//              System.out.println(letter.get(i));
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
