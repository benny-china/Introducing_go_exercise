1. How are integers stored on a computer?  
Intergers are stored on a computer by using a base-2, binary number system.  
2. We know that(in base 10) the largest one-digit number is 9 and the largest two-digit number is 99. Given that in binary the largest two-digit number is 11(3),the largest three-digit number is 111(7) and the largest four-digit number is 1111(15), what's the largest eight-digit number?  
The largest eight-digit number in binary is 255.    
4. Although overpowered for the task, you can use Go as a calculator.Write a program that computes 32,132x42,452 and prints it to the terminal(use the * operator for multiplication).  
The following is the answer.  
````golang
package main
import "fmt"
func main() {
    fmt.Println(32132*42452)
}
````
5. What is a string? How do you find its length?  
A string is a sequence of characters. You can find the length of a string using the len function.  
7. What's the value of the expression (true && false) || (false && true) || !(false && false) ?  
The value of the expression is true.
