1. Install go using instructions from the website
1. 
```bash
mkdir go_projects
cd go_projects
go mod init <name> # to initialize you go module/folder/program
nvim go.mod # a go.mod file is auto generated 
cd go_projects # go back to the go_projects parent folder and structure you code 
nvim -p cmd/tutorial/main.go 
```
1.
```go-lang
package main
import "fmt"

func main() {
    fmt.Println("Hello World!")
    var a_number int = 32 
    var a_name = "name"
    an_infered_name := "name"
    var one, two, three, four int = 1, 2, 3, 4
    var1, var2, var_end := 9, 3, "end"
    const USER = "admin"
    printf("hello, %v. How are you doing at %v ?", name, place)
}
```

1. 
```bash
go build cmd/tutorial/main.go # this will build the go program into binary
./main
go run cmd/tutorial/main.go # this will complile and run in one command 
```

# Mastering Go: A Comprehensive Guide to Golang Programming
1. go and install the go compiler from `go.dev`
1. install go and `code runner` extension for vscode
1. install some go dependencies
1. get go snippets; and paste a simple hello word program
1. run `go mod init <name>`

# go-lang
## Installation and setup
1. Goto `https://go.dev/doc/install`
  ```bash
      go --version # to check if go is installed 

      mkdir go_projects
      cd go_projects
      go mod init <name> # to initialize you go module/folder/program
      nvim go.mod # a go.mod file is auto generated 
      cd go_projects # go back to the go_projects parent folder and structure you code 
      nvim -p cmd/tutorial/main.go 
      go build cmd/tutorial/main.go && ./main 
      go run cmd/tutorial/main.go 
  ```

##  Hello World
```go
    package main

    import "fmt"

    func main () {
      fmt.Println("Hello World")
    }
```

## Variable Types
  ```go
      package main

      import "fmt"
      import "unicode/utf8"

      func main () {
        var intNum int = - 32767  // you can have type int, int8, int16, int32, int64 
        var uintNum uint = 32767 // you can have type uint, uint8, uint16, uint32, uint64 
        var floatNum float32 // you can have type float32 and float64
        fmt.Println(intNum, uintNum, floatNum)

        // mixing or performing operations on variables
        var result float32 = floatNum + float32(intNum)
        fmt.Println("The result to mixing vars", result)

        x, y := 3, 2
        fmt.Println("The result to Interger division", x/y)
        fmt.Println("The remainder of Interger division", x%y)

        // Strings
        var myString string = "Hello World \n"
        var myMultiString string = `Hello
        World`
        fmt.Println(myString, myMultiString)
        fmt.Println(len("test")) // this returns the number of bytes and not actual length
        fmt.Println(utf8.RuneCountInString("test")) // this returns the number of bytes and not actual length

        // Runes 
        var myRune rune = 'a'
        fmt.Println(myRune)

        // Booleans
        var myBoolean bool = true 
        fmt.Println(myBoolean)

        // Constants
        const myConst string = "I cannot change this"
        fmt.Println(myConst)
      }
  ```

> [!NOTE]
> Interger division returns whole numbers
> learn difference of float32 and float64 and how they are stored
> learn the min and max of the ints, and uints

## Functions and Control Structures
  ```go
    package main

    import (
      "fmt"
      "errors"
    )


    func main () {
      text := "Hello"
      printMe(text)
      result, remainder, err := divide(2, 4)
      if err != nill {
        fmt.Printf(err.Error())
      }else if remainder == 0 { // you can also have &&, || conditions
        fmt.Printf("The result is %v", result)
      }else {
        fmt.Printf("The result %v and the remainder %v", result, remainder)
      }

      switch {
        case err!=nill:
          fmt.Printf(err.Error())
        case remainder == 0:
          fmt.Printf("The result is %v", result)
        default:
          fmt.Printf("The result %v and the remainder %v", result, remainder)
      }

      switch remainder{
        case 0:
          fmt.Printf("The division was exact")
        case 1, 2:
          fmt.Printf("The division was close")
        default:
          fmt.Printf("The division was not close")
      }
    }

    func printMe (printValue string) {
      fmt.Println(printValue)
    }

    func divide (x int, y int) (int, int, error) {
      var err error
      if y == 0 {
       err = errors.New("Cannot divide by zero (0)") 
        return 0, 0, err
      }
      result := x / y
      remainder := x % y
      return result, remainder, err
    }
  ```

## Arrays, Slices, Maps and Looping control structure
```go
    package main

    import "fmt"

    func main () {

      // Arrays

      // var intArr [3]int32
      var intArr [3]int32 = [3]int32{1, 2, 3} 
      // [3]int32 := [3]int32{1, 2, 3} 
      // [3]int32 := [...]int32{1, 2, 3} // the compiler will infer the number of items in the array
      intArr[1] = 123 
      fmt.Println(intArr[0])
      fmt.Println(intArr[1:3])
      fmt.Println(&intArr[1]) // Show where they are stored in memory

      // Slices
      var intSlice []int32 = []int32{4, 5, 6}  // by omitting the length value, we now have a slice 
      fmt.Printf("The length of the slice is %v with capacity %v \n", len(intSlice), cap(intSlice))
      intSlice = append(intSlice, 7)
      fmt.Printf("The length of the slice is %v with capacity %v \n", len(intSlice), cap(intSlice))
      fmt.Println(intSlice)

      // you can  also append multiple items to a slice by using a spread operator like this 
      var secondIntSlice []int32 = []int32{7, 8, 9}  // by omitting the length value, we now have a slice 
      intSlice = append(intSlice, secondIntSlice...)

      // you can also use make to create a slice 
      var intSlice3 []int32 = make(int32[], 3, 8) // this creates a slice of type int32, length 3 and 8 for the capacity to solve performance from reacclocationk

      // Maps 
      var myMap [string]uint8 = make(map[string]uint8) // this creates a map of string as the key type and unit8 as the value type
      var myMap2 = map[string]uint8{"Adam": 23, "Sarah": 45}
      fmt.Println(myMap2["Adam"])
      fmt.Println(myMap2["Jacob"]) // this will refurn the default of uint8: 0 
      value, exist := myMap2["Adam"]
      if exist {
          fmt.Printf("The age is %v", age)
      }else{
          fmt.Println("Invalid name")
      }
      delete(myMap2, "Adam")

      // Looping
      for name, age := range myMap2 {
        fmt.Printf("Name: %v, Age: %v \n", name, age)
      }

      for i, v := range intArr {
        fmt.Printf("Index: %v, Value: %v \n", i, v)
      }

      for i :=0 , i>10 {
        fmt.Println(i)
        i++
      }
      // OR
      for { 
        i := 0
        if i  >= 10 {
          break
        }
        fmt.Println(i)
        i++
      }
      // OR
      for i :=0 , i>10, i++ {  // this logic an also apply to other things like
        // for create(), condition_for_stopping(), run_after_each_loop()
        fmt.Println(i)
      }
    }
```

>[!Note]
> learn about utf-8 
> learn about the fmt.Printf

## Strings and Runes
```go
    // runes 
    nyRune := []rune("resume") // supposed to be the french resume
    
```

>[!Note]
> learn about string and string builder
> learn about the fmt.Printf

## Structs and interfaces
