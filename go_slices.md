Go Slices
---------

[Go slices blog post](http://blog.golang.org/slices)

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
