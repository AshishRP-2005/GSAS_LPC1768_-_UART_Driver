## Day 1
# C_Pointers
## What are pointers?
- They are according to my understanding, a variable that stores the memory address of another variable
- Declaration - `data_type *pointer_name` - declares that `pointer_name` can be used as a pointer
- Derefernce - `*pointer_name` - Acess the value prestent in the memory address
- This stores the memory_adress of the variable in the pointer variable

## & operator
- The `&` operator basically let's you access the address
- `variable_name = &pointer_name`
- This provides the memory_address of pointer_name

## Example
`int x = 10;
int *ptr = &x;
*ptr = 20;`

## Other use case
- Array - `int *ptr = arr` - points to the memory_address of the first value, `*(ptr+1)` accesses the value of the next one and so on 
- Linked list - points at one end to another beginning
- Dynamic memory allocation

## why Pointers?
I had this question why increase complexity by using pointers, and i found out that the reason is it allows for direct action on memory, which is very useful in hardware coding and data set building.
