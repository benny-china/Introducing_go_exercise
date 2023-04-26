1. What's the difference between a method and a function?  
The difference between a method and a function is that a method has a receiver while a function does not.  
2. Why would you use an embedded anonymous field instead of a normal named field?  
You would use an embedded anonymous field instead of a normal named filed in order to use mehtods directly on the containing type.  
3. Add a new perimeter method to the Shape interface to calculate the perimeter of a shape. Implement the method for Circle and Rectangle.  
````golang
package main
import (
    "fmt"
    "math"
)

type Shape interface {
    perimeter() float64
}

type Circle struct {
    x,y,r float64
}

type Rectangle struct {
    x1,y1,x2,y2 float64
}

func distance(x1, y1, x2, y2 float64) float64 {
    a := x2-x1
    b := y2-y1
    return math.Sqrt(a*a + b*b)
}

func(c *Circle) perimeter() float64 {
    return math.Pi*c.r*2
}

func(r *Rectangle) perimeter() float64 {
    l := distance(r.x1, r.y1, r.x1, r.y2)
    w := distance(r.x1, r.y1, r.x2, r.y1)
    return 2*(l+w)
}

func main() {
    c:=&Circle{0,0,2}
    r:=&Rectangle{1,1,3,2}
    fmt.Printf("circle p=%.2f\n", c.perimeter())
    fmt.Printf("rectangle p=%.2f\n",r.perimeter())
}
````
