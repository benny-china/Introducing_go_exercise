1. Writing a good suite of tests is not always easy, but the process of writing tests often reveals more about a problem than you may at first realize. For example, with our Average function, what happens if you pass in an empty list ([]float64{})? How could the function be modified to renturn 0 in this case?  
``````golang
func Average(xs []float64) float64 {
    if len(xs) == 0 {
        return 0;
    }
    total := float64(0)
    for _,x:=range xs {
        total += x
    }
    return total / float64(len(xs))
}
``````
2. Write a series of tests for the Min and Max functions you wrote in the previous chapter. 
``````golang
package my_math
import "testing"

func TestMyMath(t *testing.T) {
    cases := []struct {
        xs      []float64
        max,min float64
    } {
        {
            xs: []float64{3,5,2,1,7,9},
            max:9,
            min:1,
        },
        {
            xs: []float64{},
            max:0,
            min:0,
        },
    }

    for _,c:= range cases {
        max := Max(c.xs)
        if max != c.max {
            t.Errorf("expected %f got %f",c.max, max)
        }
        min := Min(c.xs)
        if min != c.min {
            t.Errorf("expected %f got %f",c.min, min)
        }
    }
}
``````
