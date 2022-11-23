# CPPRevisionPoints

## Book Followed 
Object oriented By E balagurusamy

Day  1 Principles of Object Oriented programming

### Procedural Programming
- In POP it consists of writing a list of instructions for computer to follow and organise these instructions into groups known as Functions.
- Important data item are placed as Global so that they may accessed by all functions. Therefore data is vulnerable.
- Doesn't model real world problem well, Doesn't incorporates real world entity.
- Functions are action-oriented.
- POP Features
  - Emphasis on algo
  - Divide into functions.
  - Share global data
  - Data move freely
  - Follows top down

### Object Oriented Programming
- OOPS a paradigm in which we divide our problems into entities called Objects and then build data and function around these objects.
- Alternatively, It is a way of modularizing programs by creating a partitioned memory area for data and function that are enclosed together in a class and can create copies of such modules on demand
- OOPS Features
  - Emphasis on data rather functions.
  - Programs divided into objects.
  - Functions that operate on it will be tied together in data structure
  - data is hidden by using access modiifers.
  - Follows bootom up 
  - Objects can communicate.
 - #### Class - Class is a user defined data type which is basically a blueprint that shares same characteristics(data) or behaviour(function) that is common to all objects. It is group of variables of different types. Class doesn't occupy memory.
 - #### Objects - Run time entity that have state(data members), behaviour(member function),id(unique id)
 - #### Encapsulation - Wrapping up of data and function into a single unit is known as encapsualtion. Data is not accessible to outside world.
 - #### Abstraction - It refers to the act of representing essential features without including the background details or explanation.
 - #### Inheritance - Objects of one class derive the properties of object of other class.
 - #### Polymorphism - Ability of a function and operator to take more than form. An Operation may exhibit different behaviour in different instances. The behaviour depends upon the types of data used in operation.
 - #### Dynamic Binding - Binding refers to the linking of procedure call to the code to be executed in reponse to the call. Dynamic binding means that code associated with a given procedure call is not known untill the time of the call at run time. It is associated to polymorphishm and inheritance.
 - #### Message Passing - Objects communicate with one other by sending and receiving info.It specifies the name of object and name of function and information(arguments) to be sent.
 
 - Object based programming supports encapsulation and object identity(ex ada) while oops has inheritance + dynamic binding as well(ex C++)
 
 
 
 - Day 2 (Beginning with c++)
 
 - Developed by Bjarne stroustrap
 - c++ superset of c
 - All c programs are c++ programs but vice versa not true and maybe some c program not work under c++ compiler
 - Applications of C++:-
   - Allows to make object oriented libraries that can use later.
   - C++ map real world problems while its part c gives more ability to machine level details.
 - << is insertion or put to operator. where >> is extraction or get to operator.
 - Namespace provide the space or scope where we can define or declare identifier i.e. variable,  method, classes.
   - Example, you might be writing some code that has a function called xyz() and there is another library available which is also having same function xyz(). Now the compiler has no way of knowing which version of xyz() function you are referring to within your code.
 - In C Namespace,Refrence variable,virtual and friend function not supported and no strict type checking.
 - main function should have a return type as zero to avoid warnings or errors.
 - Default return type for all functio in c++ is int.
 - cin can read only name without spaces.

### Chapter 3 (Tokens, Expressions, and control structures)

- Identfier can't start with digit, can't use keyword.
- C has limit of 32 characters in name while c++ has no limit
- c++ has 95 keywords.
- in c++ int = 2 bytes long int = 4 bytes float = 4 bytes and double = 8 bytes
- void pointer or generic pointer has no associated data type instead it can point to any basic type but can't be derefrenced. and need type casting as well
  - *ip  = *gp if gp is void bcz it doesn't make sense to dereference a void pointer
  - C++ doesn't allow arithmetic operators.
  - malloc and calloc returns void pointer.
- Enumerated data type assigns name to numbers, thereby increasing comprehensibility of the code. for example it automatically enumerates a list of words by assigning them values 0,1,2 etc
  - enum shape {circle,square}; shape ellipse; shape back = 7 // Not allowed.
- In c++, character array length must be one larger than total characters. 
- char * const ptr1 = "Good"; constant pointer;  the pointer points to a fixed memory location, and the value at that location can be changed because it is a variable, but the pointer will always point to the same location because it is made constant here.
- int const * ptr2 = &m; pointer to constant . It can points to any variable of correct type but contents of what it points to cannot be changed
- const char * const ptr3 = "cy" constant pointer to constants In the constant pointers to constants, the data pointed to by the pointer is constant and cannot be changed. The pointer itself is constant and cannot change and point somewhere else.

- reference variable is like an alias to previously defined variable like, must be initialized, its application is passing arguments to functions
```
int sum = 5;
int &s = sum;
```
```
int x;
int *p = &x;
int &m = *p; 
int &k = 7 // allowed
```

- Scope Resolution operator:-
  - scope is the area of the program upto which a variable is accessible, c++ is block scoped
  - c++ provides SRO that is an operator that allows to access the global version of  a variable
  - It Allows us to access the global version of a variable.
  - Major application of SRO is to identify the class to which a member function belongs to.
  
- Member dereferncing operator:-
  - permits to access class members through pointers
  ```
  ::* - pointer to member of a class
  * - access member using object name and a pointer to that member
  ->* - access member using a pointer to object and a pointer to that member.
  ```
  - malloc() and calloc() for memory allocation while new and delete are operator for memory allocation
  
  ```
  int *p = new int(5);
  int *ar = new int[10];
  ```
  
  
  ```
  array_ptr = new int[3][5][4]; // illegal first one can be constant or variable but other need to constant
  array_ptr = new int[][3][6] // illegal
  delete [size] pointer_var // for deleting array of given size
  delete [] arrayP // delete complete array pointer
  
  ```
  
  - Advantages of new operator:-
   - automaticaly computes size of given data type
   - automatically returns coorect pointer no need for type cast whereas malloc return void pointer 
   - can do initialization
   - can be overloaded 
  - malloc() vs calloc():-
    - **malloc()** :- 
      - malloc() doesn’t initialize the allocated memory. If you try to read from the allocated memory without first initializing it, then you will invoke undefined behavior, which will usually mean the values you read will be garbage.
      - takes single arguments i.e, number of bytes to be allocated like 5*sizeof(int);
      - faster
      - It is used to indicate memory allocation
    - **calloc()** :- 
      - calloc() allocates the memory and also initializes every byte in the allocated memory to 0. If you try to read the value of the allocated memory without initializing it, you’ll get 0 as it has already been initialized to 0 by calloc().
      - takes two args (no of blocks required, size of each block) example calloc(5,sizeof(int));
      - slower
      - It is used to indicate contiguous memory allcoation

    - endl vs \n 
     - cout << endl inserts a new line and flushes the stream(output buffer), whereas cout << “\n” just inserts a new line.
     - endl is manipulator and \n is character.
     

### Chapter 4 - Functions in c++
- The prototype describes the function interface basically the return type,arguments,and function name but not the definition
- a template is also used to ensure that proper arguments passed and return value is treated correctly.
- In c empty parenthesis defines any number of arguments but in c++ it means empty arguments list
- In c++ it can have open parameter list using ellipses int functionname(...);
- In c++ we can use call by reference using & but in c it is applied using pointers and indirection.
- inline function is a function that expanded in line when it is invoked.
- In the case of inline, the arguments are evaluated only once.Whereas in the case of macro, the arguments are evaluated every time whenever macro is used in the program.
- macros do not have error checking while inline have error checking.
** Function Overloading resolution :-**
   - tries to find exact match.
   - If not found it uses integral promotion to actual args like float to double and char to int
   - when both fails it uses implicit conversion but if multplie matches arises then it gives an error messages
   - If all fails compiler will try the user defined conversions.
 
### Chapter 5 Classes and Objects 





