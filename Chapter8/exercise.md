1. Why do we use packages?  
Packages are a good software engineering practice. They allow us to break up large programs into smaller, easier to understand, and easier to maintain programs. They also encourage software reuse.  
2. What is the difference between an identifier that starts with a capital letter and one that doesn't?  
Identifiers that start with a capital letter are exported, whereas identifiers that start with a lowercase letter are not.  
3. What is a package alias? How do you make one?  
A package alias is an alternative name for a package that you can specify when you import the package: import f "fmt".  
4. We copied the average function from Chapter 6 to our new package. Create Min and Max functions that find the minimum and maximum values in a slice of float64s.
`````` golang
package my_math
func Max(xs []float64) float64 {
    var max float64
    for i,x := range xs {
        if i==0 || x>max {
            max = x
        }
    }
    return max
}

func Min(xs []float64) float64 {
    var min float64
    for i,x := range xs {
        if i==0 || x<min {
            min = x
        }
    }
    return min
}
``````
5. How would you documnet the functions you created in #4?
