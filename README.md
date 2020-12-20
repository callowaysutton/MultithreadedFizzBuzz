# MultithreadedFizzBuzz
A multithreaded FizzBuzz implementation

Uses waitgroups (https://gobyexample.com/waitgroups) to parallelize FizzBuzz

It is around 4x faster than this one I made in 2 minutes:
```go
package main

import (
	"fmt"
	"os"
	"strconv"
)

func main() {
	input, err := strconv.Atoi(os.Args[1])
	if err != nil {
		panic(err)
	}

	for i := 1; i <= input; i++ {
		switch true {
		case i%3 == 0:
			fmt.Print("Fizz")
			break
		case i%5 == 0:
			fmt.Print("Buzz")
			break
		case i%15 == 0:
			fmt.Print("FizzBuzz")
			break
		default:
			fmt.Printf("%d", i)
			break
		}
		fmt.Print("\n")
	}
}

```
Which makes sense considering it's using 4 goroutines :P



## Multithreaded:

```PS
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 845
Ticks             : 18456926
TotalDays         : 2.13621828703704E-05
TotalHours        : 0.000512692388888889
TotalMinutes      : 0.0307615433333333
TotalSeconds      : 1.8456926
TotalMilliseconds : 1845.6926
```
## Non-Multithreaded:
```PS
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 8
Ticks             : 80085322
TotalDays         : 9.26913449074074E-05
TotalHours        : 0.00222459227777778
TotalMinutes      : 0.133475536666667
TotalSeconds      : 8.0085322
TotalMilliseconds : 8008.5322
```
