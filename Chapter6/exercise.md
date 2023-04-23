1. sum is a function that takes a slice of numbers and adds them together. What would its function signature look like in GO?  
The sum function signature in GO looks like : func sum(val int[]) int.  
2. Write a function that takes an integer and halves it and returns true if it was even or false if it was odd. For example, half(1) should reutrn (0,false) and half(2) should return (1,true).  
````golang
package main
import "fmt"
func main() {
    fmt.Println(half(7))
}

func half(num int) (int,bool) {
    return num/2, num%2==0
}
````  
3. Write a function with one variadic parameter that finds the greatest number in a list of numbers.  
````golang
package main
import "fmt"

func main() {
    max := max_num(1,2,4,4,23,2,36,15)
    fmt.Println(max)
}

func max_num(args... int) int {
    max:=0
    for k,v:=range args {
        if k==0 || v>max {
            max = v
        }
    }
    return max
}
````
4. Using makeEvenGenerator as an example, write a makeOddGenerator function that generates odd numbers.  
````golang
package main
import "fmt"

func makeOddGenerator() func() uint {
    i := uint(1)
    return func() (ret uint) {
        ret = i
        i += 2
        return
    }
}

func main() {
    nextOdd := makeOddGenerator()
    fmt.Println(nextOdd())
    fmt.Println(nextOdd())
    fmt.Println(nextOdd())
    fmt.Println(nextOdd())
}
````  

5. The Fibonacci sequence is defined as: fib(0)=0,fib(1)=1,fib(n)=fib(n-1)+fib(n-2).Write a recursive function that can find fib(n).  
````golang
package main
import "fmt"
func fib(n int) int{
    if n==0 || n==1 {
        return n
    }
    return fib(n-1)+fib(n-2)
}

func main() {
    res := fib(9)
    fmt.Println(res)
}
````
6. What are defer,panic, and recover? How do you recover from a runtime panic?  
Defer defers a function to the moment before the surrounding function returns. Panic causes the function to immediately terminate along with any calling function and ultimately, the program itself. Recover is a way to prevent panics from going any further up the stack of functions. You can recover from a panic by deferring a call to a function which then calls the builtin recover function:  
````golang
package main
import "fmt"
func main() {
    defer func() {
        str:= recover()
        fmt.Println(str)    
    }()
    panic("PANIC")
}
````
7. How do you get the memory address of a variable?  
To get the memory address of a variable, use the & operator : x := &y  
8. How do you assign a value to a pointer?
10. How do you create a new pointer?  
11. What is the value of x after running this program:
````golang
func square(x *float64) {
    *x = *x * *x
}
func main() {
    x := 1.5
    square(&x)
}
````
11. Write a program that can swap two integers (x:=1; y:=2; swap(&x,&y) should give you x=2 and y=1).  
