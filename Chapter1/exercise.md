1. What is whitespace?  
Whitespace is the space between characters made up of sapce,tab and newline characters.  
2. What is a comment? What are the two ways of writing a commnet?  
A comment is a section of code ignored by the compiler that can be used as a note for anyone reading the code.  
The two types of comments are //(which goes to the end of the line) and /* */  
3. Our program began with package main. What would the files in the fmt package begin with?  
The files in the fmt package would begin with package fmt.  
4. We used Println function defined in the fmt package. If you wanted to use the Exit function from the os package, what would you need to do?  
In order to use the Exit function from the os package, you would need to import the os package and then invoke it.  
For example:  
import "os"  
os.Exit()  
5. Modify the program we wrote so that instead of printing "Hello, World" it prints "Hello,my name is" followed by your name.  
The following is the answer.  
package main
import "fmt"  
func main() {  
  fmt.Println("Hello,my name is benny.")
}
