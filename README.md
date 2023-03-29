# Check-Whether-or-Not-the-Number-is-a-Palindrome-in-Java-Language

Given an input integer as a number, the objective is to check whether or not the given number integer is a Palindrome or not in Java Language. To do so we’ll reverse the the number using the modulo and divide operators and check if the reversed number matches the original number. Here are few methods to Check Whether or Not the Number is a Palindrome in Java Language,

Method 1: Using Iteration
Method 2: Using Recursion
Let’s discuss the above mentioned methods in detail in the upcoming sections. Don’t forget to check the blue box mentioned below for better understanding of the problem.

Checking for palindrome
Table of Contents
Check Whether or Not the Number is a Palindrome in Java
Check Whether or Not the Number is a Palindrome in Java Language
Method 1: Using Iteration
Working
Java Code
Output
Method 2: Using Recursion
Working
Java Code
Output
Advanced Methods
Method 3: Using StringBuilder
Output
Method 4: Using for loop and charAt
Output
Method 5: Using with toCharArray
Output
Method 6: Using Stack
Output
Prime Course Trailer
Related Banners
Working with Numbers
Method 1: Using Iteration
Working
In this method we’ll use loops to break down the number into individual digits and the reassemble them in reverse order. We’ll use the modulo operator to extract the digits and divide operator to shorten the number. Finally we’ll compare if the reversed number matches the original number.

For a given integer number variable, we perform the following operations,

Run a while loop until the condition temp variable is not 0.
Extract the digits using modulo operator.
Using the formula reverse = reverse * 10 + last digit, we’ll keep updating the reverse variable.
We’ll shorten the number using divide operator.
Check if the reversed number matches the original number.
Let’s implement the above mentioned logic in Java Language.

Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {
     //variables initialization
     int num = 12021, reverse = 0, rem, temp;

       temp = num;
     //loop to find reverse number
     while (temp != 0)
       {
     	rem = temp % 10;
     	reverse = reverse * 10 + rem;
     	temp /= 10;
       };

     // palindrome if num and reverse are equal
     if (num == reverse)
       System.out.println (num + " is Palindrome");
     else
       System.out.println (num + " is not Palindrome");
   }
 }
Output
12021 is Palindrome
Method 2: Using Recursion
Working
In this method we’ll use recursion to break down the number into individual digits and then reassemble them in reverse order. In the end we’ll check if the reversed number matches the original number.

For a given integer input as number, we perform the following,

Define a recursive function which takes the number as an argument.
Set the base case as number ==0.
Set the recursive step call as getReverse(num/10, rev).
Check if the returned value matches the original number.
Let’s implement the above mentioned logic in Java Language.

Java Code
Run
public class Main
{
  public static void main (String[]args)
  {
    //variables initialization
    int num = 12021, reverse = 0, rem, temp;

    // palindrome if num and reverse are equal
    if (getReverse(num, reverse) == num)
     System.out.println (num + " is Palindrome");
    else
      System.out.println (num + " is not Palindrome");
  }
  
  static int getReverse(int num, int rev){
    if(num == 0)
        return rev;
    
    int rem = num % 10;
    rev = rev * 10 + rem;
    
    return getReverse(num / 10, rev);
}
}
Output
21021 is Palindrome
Advanced Methods
The above programs are algorithmic methods that will work with numbers.

The below programs may be a little advanced but will work with both numeric and string inputs

Method 3 : Using StringBuilder
Method 4: Using for Loop and charAt
Method 5: Using toCharArray
Method 6: Using Stack
Method 3: Using StringBuilder
Explanation of the code mentioned in the comments below –

Run
class Main {

    public static void main(String[] args) {

        // convert these strings to either lowercase or uppercase to create consistency
        System.out.println(isPalindrome("radar".toLowerCase()));

        // Naman wouldn't have been palindrome if toLowerCase method wasn't used
        System.out.println(isPalindrome("Naman".toLowerCase()));
        System.out.println(isPalindrome("12321".toLowerCase()));
        System.out.println(isPalindrome("12345".toLowerCase()));
    }

    private static boolean isPalindrome(String string) {

        String reversed = new StringBuilder(string).reverse().toString();
        return string.equals(reversed);
    }
}
Output
true
true
true
false
Method 4: Using for loop and charAt
Explanation of the code mentioned in the comments below –

Run
class Main {

    public static void main(String[] args) {

        // convert these strings to either lowercase or uppercase to create consistency
        System.out.println(isPalindrome("radar".toLowerCase()));

        // Naman wouldn't have been palindrome if toLowerCase method wasn't used
        System.out.println(isPalindrome("Naman".toLowerCase()));
        System.out.println(isPalindrome("12321".toLowerCase()));
        System.out.println(isPalindrome("12345".toLowerCase()));
    }

    private static boolean isPalindrome(String original) {

        String reversed = "";

        int len = original.length();

        for (int i = len - 1; i >= 0; i--) {

            reversed = reversed + original.charAt(i);
        }

        return original.equals(reversed);
    }
}
Output
true
true
true
false
Method 5: Using with toCharArray
Explanation of the code mentioned in the comments below –

Run
class Main {

    public static void main(String[] args) {

        // convert these strings to either lowercase or uppercase to create consistency
        System.out.println(isPalindrome("radar".toLowerCase()));

        // Naman wouldn't have been palindrome if toLowerCase method wasn't used
        System.out.println(isPalindrome("Naman".toLowerCase()));
        System.out.println(isPalindrome("12321".toLowerCase()));
        System.out.println(isPalindrome("12345".toLowerCase()));
    }

    private static boolean isPalindrome(String original) {

        char[] data = original.toCharArray();

        int i = 0;
        int j = data.length - 1;

        while (j > i) {

            if (data[i] != data[j]) {
                return false;
            }

            ++i;
            --j;
        }

        return true;
    }
}
Output
true
true
true
false
Method 6: Using Stack
Explanation of the code mentioned in the comments below –

Please check DSA Blogs of PrepInsta here

Run
import java.util.Stack;

class Main {

    public static void main(String[] args) {

        // convert these strings to either lowercase or uppercase to create consistency
        System.out.println(isPalindrome("radar".toLowerCase()));

        // Naman wouldn't have been palindrome if toLowerCase method wasn't used
        System.out.println(isPalindrome("Naman".toLowerCase()));
        System.out.println(isPalindrome("12321".toLowerCase()));
        System.out.println(isPalindrome("12345".toLowerCase()));
    }

    private static boolean isPalindrome(String original) {

        char[] data = original.toCharArray();

        Stack stack = new Stack<>();

        for (char c: data) {

            stack.push(c);
        }

        char[] data2 = new char[data.length];

        int len = stack.size();

        for (int i = 0; i < len; i++) {

            data2[i] = stack.pop();
        }

        var reversed = new String(data2);

        return original.equals(reversed);
    }
}
Output
true
true
true
false
