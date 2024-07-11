Tag:  #daily #c #malloc

`malloc(sizeof(int))` is used to allocate memory of size equal to the size of an integer. 
The `sizeof(int)` function returns the size in bytes of an integer on your system, 
and `malloc` allocates that many bytes of memory.

```c
apointer = malloc(sizeof(int));
if (apointer == NULL)
	return 1;
```

 when you allocate memory using `malloc`, the operating system reserves a block of memory for your program to use. This memory remains reserved until you explicitly free it using `free`. If you don't free the memory when you're done with it, it remains reserved even though your program is not using it. This is known as a memory leak.

Memory leaks can be a problem because they reduce the amount of memory available for other programs. If a program has many memory leaks, or if it runs for a long time and continually leaks memory, it can consume all of the available memory and cause the system to run out of memory.

Here's a short example of how to correctly allocate and free memory in C:

```c
int *p = malloc(sizeof(int));
if (p == NULL)
	return 1;

*p = 42;
free(p);
```

In this code, `malloc(sizeof(int))` allocates memory for an integer. The returned pointer is stored in `p`. The memory is then used to store the value `42`. 
When we're done with the memory, we call `free(p)` to release it back to the system.

If we didn't call `free(p)`, the memory would remain reserved until the program exits. 
This would be a memory leak.

When you call `free(p)`, the memory that was previously allocated with `malloc` is released back to the system and can be reused for other operations. 

If you don't call `free(p)`, that memory remains reserved for your program, even if your program is not using it. 