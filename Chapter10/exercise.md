1. How do you specify the direction of a channel type?  
You specify the direction of a channel type by using <-：
2. Write your own Sleep function using time.After.  
``````golang
func Sleep(interval time.Duration) {
    <- time.After(interval)
}
``````
3. What is a buffered channel? How would you create one with a capacity of 20?  
A buffered channel allows send operations to succeed regardless of whether or not there is a receiver on the other end by storing the sent message in a buffer. To create a buffered channel, specify a buffer size as an argument to make: make(chan int, 20).  
