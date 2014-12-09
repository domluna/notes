Go Slices
---------

[Go slices blog post](http://blog.golang.org/slices)

### Main point 

Go slices are passed by value. However the internal structure of a slice
is as follows: 

type sliceHeader struct {
  Length int
  ZerothElement \*byte
}

This isn't the complete definition but it gets the point across. 

The thing to note here is the ZerothElement field is a pointer to a byte.
If the field of a struct that's passed by value is a pointer that field
can be altered.

For slices this is particularly useful since we can pass them by value
and not think twice yet not be bit by the overhead of passing a huge structure
by value would bring.

### Example

The example below shows that if the underlying data is a pointer we can
just pass things around by value.

```go
        package main

        import "fmt"

        type blob struct {
	        cap int
	        data []int
        }

        func newBlob(cap int) blob {
	        return blob{
		        cap: cap,
		        data: make([]int, cap),
	        }
        }

        func mutateDataFunc(b blob) {
	        b.data[0] = 500
        }

        func (b blob) mutateDataMethod() {
	        b.data[0] = 250
        }

        func main() {
	        b := newBlob(10)
	        fmt.Println(b)
	        mutateDataFunc(b)
	        fmt.Println(b)
	        b.mutateDataMethod()
	        fmt.Println(b)
        }
```

Output:

```sh
{10 [0 0 0 0 0 0 0 0 0 0]}
{10 [500 0 0 0 0 0 0 0 0 0]}
{10 [250 0 0 0 0 0 0 0 0 0]}
```
