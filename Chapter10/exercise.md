1. How do you specify the direction of a channel type?  
You specify the direction of a channel type by using <-：
2. Write your own Sleep function using time.After.  
``````golang
func Sleep(interval time.Duration) {
    <- time.After(interval)
}
``````
3. What is a buffered channel? How would you create one with a capacity of 20?  
