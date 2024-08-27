This repository offers a comprehensive overview of undefined behaviors, implementation-defined behaviors, and unspecified behaviors in programming. It includes detailed lists and explanations of each topic.


## Undefined Behavior

So why is there undefined behavior?

Its reason for existence is to ensure that compilers perform good optimizations. What does the compiler rely on to optimize? It optimizes by relying on the absence of undefined behavior in the code.

* Undefined behavior is a matter of compiler optimization. Modern compilers rely on the absence of any case of undefined behavior. 
* When runs the code which has a undefined behavior that means all bets are off. It can be anything in run time.

* Undefined Behaviors Situations in C Programming Language

1) Automatically-lived variables come to life as garbage. Using garbage values ​​is undefined behavior.
2) Undefined behavior in the integer division by 0 operation.
3) Accessing a non-existent index of an array is undefined behavior.
4) This is undefined behavior. An object was subjected to a side effect within an expression, but the same object was reused before the sequence point passed.
   int main(void)
   {
       int x = 20;
       int y = x + x++;
   }

5) If we are performing arithmetic operations, overflow on signed types is undefined behavior.
6) No syntax error but undefined behavior. They are doing it on the embedded side.

An attempt to modify an object that is itself const is undefined behavior. Removing the syntax obstacle does not change the fact that it is ub. This is definitely undefined behavior.

    const int x = 10; 
    int *p = (int*)&x; 
    *p = 4564;
    
7) A function should not return an address of an automatically-lived object. Undefined behavior. Static eliminates ub.

     int* scan_x(int ival)
     {
         int ret = ival;
         return &ret;
     }

     int main(void)
     {
       int* p;
       p = scan_x(45);
       printf("%d", *p);
     }


8) We can dereference a pointer that points to an object.
  If I dereference a pointer that holds the address of the end of an array, undefined behavior.
  A pointer whose value is a NULL pointer should never be dereferenced. Undefined behavior.

9) String literals are arrays that can be used for read-only purposes.
   When we look at the static type system in the C language, while there are char arrays, string literals are immutable arrays.
   Attempting to change a string literal is undefined behavior. Undefined behavior.

    char* pname = “Cetin”; 
    *pname = ‘M’



10) Attempting to return a memory block that was not dynamically acquired is undefined behavior.
    Attempting to reduce a memory block acquired with malloc/calloc/realloc by calling the free function is undefined behavior. You can do this with realloc.
    Dereferencing a dangling pointer that holds the address of a memory block that has been freed - whether for reading or writing - is undefined behavior.
    not free ====> memory leak

    Dereferencing a freed memory block is undefined behavior.
    Re-freeing a freed memory block —> double free is undefined behavior.



11) Directly dereferencing a void pointer will result in undefined behavior.
    Since void pointers do not point to a specific data type, it is necessary to determine the type of these pointers when reading or writing data from memory.
    Otherwise, the compiler may not know the data type and may perform incorrect memory operations.
    Undefined behavior can cause the program to work unexpectedly or crash. Therefore, it is important to convert a void pointer to a suitable data type in order to dereference it.






   
