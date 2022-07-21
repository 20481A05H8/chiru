# chiru
1. Make a Simple Calculator using JavaScript
Solution:
let output;
const operator = prompt('Enter operator ( either +, -, * or / ): ');
const num1 = parseFloat(prompt('Enter first number: '));
const num2 = parseFloat(prompt('Enter second number: '));
switch(operator) {
 case '+':
 output = num1 + num2;
 console.log(`${num1} + ${num2} = ${output}`);
 break;
 case '-':
 output = num1 - num2;
 console.log(`${num1} - ${num2} = ${output}`);
 break;
 case '*':
 output = num1 * num2;
 console.log(`${num1} * ${num2} = ${output}`);
 break;
 case '/':
 output = num1 / num2;
 console.log(`${num1} / ${num2} = ${output}`);
 break;
 default:
 console.log('Invalid operator');
 break;
}
2. Validate an email address with a JavaScript programme
Solution:
// program to validate an email address
function validateEmail(email_id) {
 const regex_pattern =
/^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-
9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

 if (regex_pattern.test(email_id)) {
 console.log('The email address is valid');
 }
 else {
 console.log('The email address is not valid');
 }
}
var email1 = window.prompt("Enter an email address:");
var email2 = window.prompt("Enter an email address:");
validateEmail(email1);
validateEmail(email2);
3. Get the Dimensions of an Image using JavaScript
Solution:
const img = new Image();
// get the image
img.src = '//uploadsssl.webflow.com/60d45974277c668d0adff732/60f7bd3dc544903569f53a7d_Ban
ner%20Img.svg';
// get height and width
img.onload = function() {
 console.log('width ' + this.width)
 console.log('height '+ this.height);
}
JDBC
1. Establish a connection between Java application and Database.
import java.sql.*;
public class Sample{
public static void main(String[] args) throws Exception {
Class.forName("com.mysql.cj.jdbc.Driver");
String url = "jdbc:mysql://127.0.0.1:3306/employee";
Connection con = DriverManager.getConnection(url,"root","1234");
Statement smt = con.createStatement();
String sql1 = "Select * from emp_details";
ResultSet result = smt.executeQuery(sql1);
while(result.next()) {
System.out.print("Name is "+result.getString("Name"));
System.out.println(" and his Salary is
"+result.getString("Salary"));
}
con.close();
}
}
2. Create a Java programme to retrieve the student's highest grade from a MySQL
database.
Program - 1:
Write a Java program to check whether the number is prime or not using Junit testing.
You have to write a method isPrime which will takes an integer as parameter and return
a boolean value true if the passed value is prime or false if the value is not a prime.
Input format:
A signle line
Output format:
Print true or false by checking prime or not.
Sample Input:
3
Output:
true
Code:
class Main {
 public static void main(String[] args) {
 System.out.println("Hello world!");
 }
 public boolean isPrime(int n){
 //Write your prime check function code here
 if(n==1) return false;
 int i;
 for(i=2;i<=n/2;i++)
 {
 if(n%i==0)
 {
 return false;
 }
 }
 return true;
 }
}
Program 2
Write a Java program to reverse a string and test the test cases using Junit.
You should implement stringReverse method which takes a string as parameter and
returns a string.
Input format:
The only line contains a String.
Output format:
Return the reverse of the string.
Sample Input:
Junit Testing
Output:
gnitseT tinuJ
Code:
class Main {
 public static void main(String[] args) {
 }
 public static String stringReverse(String str){
 String rev = "";
 char ch;
 for(int i=0;i<str.length();i++){
 ch = str.charAt(i);
 rev = ch+rev;
 }
 return rev;
 }
}
Program 3
Write a Java program to find maximum number and test the test cases using Junit.
You have to write a method maxArray which takes an integer array and N that returns
the maximum element in the array.
Sample Input:
4
3 5 0 1
Output:
5
Code:
class Main {
 public static void main(String[] args) {
 System.out.println("Hello world!");
 }
 public static int maxArray(int arr[],int n){
 int max=arr[0];
 for(int i=1;i<n;i++){
 if(max<arr[i])
 max=arr[i];
 }
 return max;
 }
}
Program 1:
Create a multithreading program to demonstrate 2 thread execution.
Create the threads by implementing the Runnable.
Sample Output:
Creating Thread-1
Starting Thread-1
Creating Thread-2
Starting Thread-2
Running Thread-1
Running Thread-2
Thread: Thread-1, 4
Thread: Thread-2, 4
Thread: Thread-1, 3
Thread: Thread-2, 3
Thread: Thread-1, 2
Thread: Thread-2, 2
Thread: Thread-1, 1
Thread: Thread-2, 1
Thread Thread-1 exiting.
Thread Thread-2 exiting.
Code:
class RunnableDemo implements Runnable {
private Thread t;
private String threadName;
RunnableDemo( String name) {
threadName = name;
System.out.println("Creating " + threadName );
}
public void run() {
System.out.println("Running " + threadName );
try {
for(int i = 4; i > 0; i--) {
System.out.println("Thread: " + threadName + ", " + i);
// Let the thread sleep for a while.
Thread.sleep(1000);
}
} catch (InterruptedException e) {
System.out.println("Thread " + threadName + " interrupted.");
}
System.out.println("Thread " + threadName + " exiting.");
}
public void start () {
System.out.println("Starting " + threadName );
if (t == null) {
t = new Thread (this, threadName);
t.start ();
}
}
}
public class Examples {
public static void main(String args[]) {
RunnableDemo R1 = new RunnableDemo( "Thread-1");
R1.start();
RunnableDemo R2 = new RunnableDemo( "Thread-2");
R2.start();
}
}
Program 2:
Create a Multithreading program using Runnable Interface.
Write a program to create N threads using Runnable Interface.
Input format:
A single input contains a integer value.
Output format:
Each thread running status
Sample Input:
5
Sample Output:
Thread16is running
Thread12is running
Thread13is running
Thread14is running
Thread15is running
Note: The output may difference in case of thread id's
Code:
class MultithreadingDemo implements Runnable
{
public void run()
{
try
{
System.out.println ("Thread " +Thread.currentThread().getId() +" is
running");
}
catch (Exception e)
{
System.out.println ("Exception caught");
}
}
}
public class ImplementingRunnableInterface
{
public static void main(String args[])
{
for (int count=0; count<5; count++)
{
Thread object = new Thread(new MultithreadingDemo());
object.start();
}
}
}
Program 3:
Write a JAVA program which will generate the threads:
● To display N terms of Fibonacci series.
● To display 1 to M in reverse order.
Input format:
The first line contains N.
The next line contains M.
Output format:
print the N fibonacci series and M values in reverse order.
Note: Print every fibonacci number modulo of 100000009
Sample Input:
5
10
Sample Output:
0 1 1 2 3
10 9 8 7 6 5 4 3 2 1
Code:
import java.io.*;
import java.util.Random;
import java.util.Scanner;
class Fibonacci extends Thread
{
public void run()
{
try
{
int a=0, b=1, c=0;
 Scanner scan = new Scanner(System.in);
int n = scan.nextInt();
while (n>0)
{
System.out.print(c%100000009+" ");
a=b;
b=c;
c=a+b;
n=n-1;
}
 System.out.println();
}
catch (Exception ex)
{
ex.printStackTrace();
}
}
}
class Reverse extends Thread
{
public void run()
{
try
{
 Scanner scan = new Scanner(System.in);
int M = scan.nextInt();
for (int i=M; i >= 1 ;i-- )
{
System.out.print(i+" ");
}
}
catch (Exception ex)
{
ex.printStackTrace();
}
}
}
public class Main
{
public static void main(String[] args)
{
try
{
Fibonacci fib = new Fibonacci();
fib.start();
fib.sleep(4000);
Reverse rev = new Reverse();
rev.start();
}
catch (Exception ex)
{
ex.printStackTrace();
}
}
}
Character class:
Write a program to illustrate the concept of autoboxing and unboxing and show the use
of Character class method in Java.
Given a character you have to find whether
● it is a letter or digit
● if it is a letter then check whether a lowercase or capital case
using Character class.
input format:
A single character
Output format:
type of the given character.
● Digit
● Capital case letter
● Lower case letter
Sample Input - 1:
1
Sample Output - 1:
Digit
Sample Input -2:
a
Sample Output - 2:
Lower case letter
Code:
import java.util.*;
class Main {
 public static void main(String[] args) {
 Scanner scan = new Scanner(System.in);

 char ch = scan.next().charAt(0);
 if(Character.isDigit(ch)){
 System.out.println("Digit");
 }
 else if(Character.isLetter(ch)){
 if(Character.isLowerCase(ch)){
 System.out.println("Lower case letter");
 }
 else{
 System.out.println("Capital case letter");
 }
 }
 }
}
Override annotation
Write a program to illustrate the example of override annotation in Java.
You should have to declare two classes one parent and one child class.
You have to print the string passed to the child class method which method overrides
the parent class method.
Input format:
Two strings, one is passed to parent class method and another one is passed to child
class method.
Output format:
Print the string passed to child class.
Sample Input:
Hi Hello
Sample Output:
Child class Hello
Code:
import java.util.*;
class Company {
public void displayInfo(String str) {
System.out.println("Parent class "+ str);
}
}
class Employee extends Company {
@Override
public void displayInfo(String str) {
System.out.println(str);
}
}
class Main {
public static void main(String[] args) {
 Scanner scan = new Scanner(System.in);
 String str1 = scan.next();
 String str2 = scan.next();
 Employee e1 = new Employee();
 e1.displayInfo(str2);
}
}
     
