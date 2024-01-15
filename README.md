Problem Statement: 1) Write a program which will read temperature value in Fahrenheit scale and print the value in Celsius scale.
import java.util.Scanner; public class TempeRead {
  public static void main(String[] args) { 
    Scanner scanner = new Scanner(System.in);
    System.out.print("Temp in F: ");
    double fahrenheit = scanner.nextDouble(); 
    double celsius = fahrenheitToCelsius(fahrenheit);
    System.out.printf("Temp in C: %.2f%n", celsius); }
    
public static double fahrenheitToCelsius(double fahrenheit)
{ return (fahrenheit - 32) * 5.0/9.0; }
}


Problem Statement: 2) Write a program to enter length and width of a rectangle and find      area and perimeter of the rectangle.
import java.util.Scanner; public class AreaPeriOfRect{
  public static void main(String[] args){ 
    Scanner scanner = new Scanner(System.in); 
    System.out.print("Length of rectangle: "); 
    double length = scanner.nextDouble(); 
    System.out.print("Width of rectangle: "); 
    double width = scanner.nextDouble(); 
    double area = length * width;
    double perimeter = 2 * (length + width); 
    System.out.printf("Area: %.2f%n", area); 
    System.out.printf("Perimeter: %.2f%n", perimeter);
  }
  }


Problem Statement: 3) Write a program to enter marks of five subjects of a student and calculate total, average and percentage of all subjects.
import java.util.Scanner; 
public class Result {
  public static void main(String[] args){ 
    Scanner scanner = new Scanner(System.in); 
    double total = 0;
    for (int i = 1; i <= 5; i++) { 
      System.out.printf("Marks of Subject %d: ", i); 
      total += scanner.nextDouble();
      }
    double average = total / 5;
    double percentage = (total / 500) * 100; 
    System.out.printf("Total marks: %.2f%n", total); 
    System.out.printf("Average marks: %.2f%n", average); 
    System.out.printf("Percentage: %.2f%%%n", percentage); 
    }
 }


Problem Statement: 4) Write four statements by using printf function to print an asterisk pattern having 1, 3,5 and 7 asterisks (*) in successive lines so that it generates a triangular pattern as given below.
import java.util.Scanner; 
public class Asterisk {
  public static void main(String[] args) { 
    System.out.printf("*%n"); 
    System.out.printf(" *%n"); 
    System.out.printf(" ***%n"); 
    System.out.printf(" *****%n");
 }
 } 


Problem Statement: 5) A ball is released from a height of Y meters. Each time it bounces on the floor, its velocity becomes halved. Write a program, which reads the value of Y and prints the total distance traversed by the ball when it touches the ground for the third time. Assume that the value of acceleration due to gravity, g, is 9.8.
import java.util.Scanner; 
public class Program {
  public static void main(String[] args) { 
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter the height Y in m: "); 
    double height = scanner.nextDouble(); 
    double totalDistance = 0;
    double velocity = Math.sqrt(2 * 9.8 * height); 
    for (int bounce = 1; bounce <= 3; bounce++) {
      totalDistance += height; height /= 2; totalDistance += height;
    }

    System.out.println("Complete distance travelled by ball: " + totalDistance + " meters");
    }
}


Problem Statement: 6) Consider a bank that offers fixed deposit accounts with cumulative (annually) interest on the balance available in the account. Write a C program that reads the amount initially invested (called Principal amount) in an account and interest rate. The program generates the balance available in the account at the end of each year for first five years.
import java.util.Scanner; 
public class Ball {
  public static void main(String[] args) { 
    Scanner scanner = new Scanner(System.in); 
    System.out.print("Principal amount: "); 
    double principal = scanner.nextDouble(); 
    System.out.print("Enter the interest rate: "); 
    double interestRate = scanner.nextDouble();
    for (int year = 1; year <= 5; year++) {
      double balance = principal * Math.pow(1 + interestRate / 100, year);
      System.out.println("Balance after year " + year + ": " + balance);
    }
  }
}



