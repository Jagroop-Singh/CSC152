## Auto Allocating Arrays
Often you need to allocate memory
```
{
int x[10];	// Auto allocate 10 ints on the stack
x[5] = 3;	
...
}			// Auto deallocate
```
~ No function call: fast and convenient
~ Does not exist outside of scope
~ Runtime stack limited to 2-8KB total. Careful!

## Manually Allocating Arrays
```
{
int *y = malloc(10 * sizeof(int));
y[5] = 3;
...
free(y);
}
```
~ Function call. Remember to free when done.
~ Any size allowed. Exists after scope exits.
~ Array notation okay applied to pointer

## Array/Pointer interchangeable
