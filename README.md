# csinsertion_sort

Insertion sort algorithm implementation over a vector.

Use this create to add a ``insertion_sort`` and ``insertion_sort_by`` methods
to Vec data type.

```rust
    use csinsertion_sort::InsertionSort; 
    
    let mut input: Vec<u32> = vec![2, 1];

    // this will sort items in ascending order 
    // using insertion sort algorithm
    input.insertion_sort();
    // input is now [1,2]
```

Use ``insertion_sort_by`` to customize how items are compared. 
As second argument pass a function with the form: 
```rust 
fn(a: &T, b: &T) -> bool;
```
This function must return ``true`` to indicate that the values are not in the correct order.
For example, to sort a list of ``u32``, in descending order, ``by`` parameter can be: 
```rust
fn desc(a: u32, b: u32) -> bool {
    a < b
}
```
This example returns ``true`` when ``a=1`` and ``b==5`` in order to 
ensure that ``5`` is located at the left o ``1``.

For convenience ``asc`` and ``desc`` functions are provided. 

```rust
    use csinsertion_sort::{InsertionSort, des}; 
    
    let mut input: Vec<u32> = vec![1, 2];

    // this will sort items in descending order 
    // using insertion sort algorithm
    input.insertion_sort_by(desc);

    // input is now [2,1]
```

To call ``insertion_sort`` is equivalent to call ``insertion_sort_by(asc)``.