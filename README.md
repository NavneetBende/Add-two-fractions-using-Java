# Add-two-fractions-using-Java
Add two fractions using java 
In this article we will discuss the program for add two fractions using java. For this purpose we need to ask the user to enter two fractional values where each fraction must consist a Numerator and a Denominator.

add two fractions using java
Concept
 For understanding this in a better way lets suppose an example :

 Suppose, First fraction consist of 1 as numerator and 3 as denominator, and Second fraction consist of 3 as numerator and 9 as denominator.

 (1 / 3) + (3 / 9) = (6 / 9) = (2 / 3)

Find LCM of 3 and 9 and the result will be 9.
Multiply 3 in first fraction : (3 / 9) + (3 / 9)
Add both fractions and then the result will be : (6 / 9)
Now simplify it by finding the HCF of 6 and 9 and the result will be 3.
So divide 6 and 9 by 3 and then the result will be : (2 / 3)
This will be your simplified answer for the given problem.
Algorithm
Initialize variables of numerator and denominator
Take user input of two fraction
Find numerator using this condition (n1*d2) +(d1*n2 ) where n1,n2 are numerator and d1 and d2 are denominator
Find denominator using this condition (d1*d2) for lcm
Calculate GCD of a this new numerator and denominator
Display a two value of this condition x / gcd, y/gcd
add two fractions
Related Pages
Permutations in which n people can occupy r seats in a classroom
 
Maximum number of handshakes
 
Replace all 0’s with 1 in a given integer

Can a number be expressed as a sum of two prime numbers

Count possible decoding of a given digit sequence

Java code
Run
//Java program to add two fractions
import java.util.Scanner;
public class Main
{
	public static void main(String[] args)
	{
		//scanner class declaration
		Scanner sc = new Scanner(System.in);
		//input from the user		
		System.out.print("Enter numerator for first fraction : ");		
		int num1 = sc.nextInt();
		System.out.print("Enter denominator for first fraction : ");		
		int den1 = sc.nextInt();
		System.out.print("Enter numerator for second fraction : ");		
		int num2 = sc.nextInt();
		System.out.print("Enter denominator for second fraction : ");		
		int den2 = sc.nextInt();
		int num, den, x;
		System.out.print("("+num1+" / "+den1+") + ("+num2+" / "+den2+") = ");
		//logic for calculating sum of two fractions
		if(den1 == den2)
		{
			num = num1 + num2 ;
			den = den1 ;
		}
		else{
			num = (num1*den2) + (num2*den1);
			den = den1 * den2;
		}
		if(num > den)
			x = num;
		else
			x = den;
		for(int i = 1 ; i <= x ; i++)
		{
			if(num%i == 0 && den%i == 0)
			{
				num = num/i;
				den = den/i;
			}
		}
		//logic for getting simplified fraction
		int n = 1;
		int p = num;
		int q = den;
		if( num != den)
		{
			while(n != 0)
			{
				//storing remainder
				n = num % den;			
				if(n != 0)
				{
					num = den;
					den = n;
				}
			}			
		}
		System.out.println("("+p/den+" / "+q/den+")");
		//closing scanner class(not compulsory, but good practice)
		sc.close();									
	}
}
Output
Enter numerator for first fraction : 1
Enter denominator for first fraction : 3
Enter numerator for second fraction : 3
Enter denominator for second fraction : 9
(1 / 3) + (3 / 9) = (2 / 3)
