# DART



## INTRO

**Syntax:**

```dart
import "dart:core";
import "dart:io"; //for input output operations
   
main(){
	print("Hello world \n");
}
```

Dart is Similar to JavaScript and also dynamically typed and statically typed also.



### Variable Types

There are variables types like ```int``` ```double``` ```string``` ```boolean``` and a special type called ```dynamic``` and this ```dynamic``` datatype variable doesn't have any specific data type through out the code i.e, we can change the same variable from integer to string to boolean etc...

**Declaring the variables using ```var``` keyword:**

```dart
main(){
    var temp = 1; //declaring variable using var keyword
    print(temp);
    temp = 2.39; 
    //this is not valid as second time it's a double instead of integer
    print(temp); //gives error as said above
}
```

**Declaring the variables using ```dynamic``` keyword:**

```dart
main(){
	dynamic temp = 1; //declaring variable using dynamic keyword
    print(temp);
    
    temp = "hello";
    print(temp)
}

// this is also valid
```



#### Reading inputs:

```dart
import "dart:core";
import "dart:io"; //for input output operations
   
main(){
	stdout.writeln("Enter a number:"); //similar to print statement
    var inp = stdin.readLineSync();    //similar to cin in C++ but reads an entire line
    print("You have entered $inp");	   //'$' for accessing the variable value 
}
```

Here, for printing a variable in the print statement we have used ```$``` symbol for accessing it's value.



#### Comments:

we can either use ```//``` or ```/* */``` for line comment and block comment respectively. ```///``` for documentation.



#### Formatting strings:

We can either use single quotes ```''``` or ```""``` for strings but when we are writing a word like ```it's``` then we need to write it as ```it\'s``` if we are using ```''``` to start and end a string.

```dart
main(){
	String s1 = 'It\'s not an issue';
    String s2 = "It's not an issue";
    
    String s3 = r'Its not an issue \n no newline here'; 
    // adding r infront of the string tells that it's a raw string meaning no special charecters like \n
}
```

```dart
main(){
	String s1 = '''It\'s not an issue
	Hello''';
    
    // this is a multi line string
    
    String s2 = """It's not an issue
    Hello world""";
}
```



### Type Conversions:

we can use ```parse()``` function for parsing a string and converting it to other datatypes.

```dart
var numb = int.parse("34");
assert(numb == 34);

//assert() just checks for the datatype equality
//if same noe error (nothing printed also)
//else error

var numb1 = double.parse("34.2");
assert(numb1 == 34.2);
```



> 1. **const** keyword: 
>
>    We can also use ```const ```  keyword for constants.
>
> 2. int n; 
>
>    print(n);  ->  this prints null by default.

>3. runtimeType: 
>
>   This lets us know the run time type of a variable
>
>   eg:
>
>   ```dart
>   main(){
>       var temp = 0;
>       print(temp.runtimeType); //prints int
>   }
>   ```

## Operators:

```dart
+, -, /, % //are the arithmetic operators
++, --, //are also the arithmetic operators
&&, || etc.. //for binary 
    
//similar operators as in other languages
```



### If statements and Loops:

Similar to other languages

```dart
if (n != 2){
    print("n not equal to 2")
}else{
    print("n is equal to 2")
}
```

```dart
for(int i=0;i<2;i++){
    print(i);
}
```

 

**Null Aware Operator:**

1. ```?.``` operator:

   in case of objects this operator checks if we are fetching a valid object if so no problem else this returns null (if done normally it gives an error)
   **Eg:** 

   ```dart
   class node{
       int num = 10;
   }
   
   main(){
       var n = node();
       int number;
       
       //checks if there is property named 'num' for the 'n' object 
       number  = n?.num ?? 0; 
       //if object doesn't have such property or object is invalid then it returns null
       print(number);
   }
   ```

   

2. ```??``` operator:

   Checks if a variable is null.

3. ```??=``` operator:

   Checks a variable is null or not and assigns a value if it's not.

   ```dart
   main(){
       int num;
       num ??= 10;
       print(num); 
       //prints 10 since num is null in previous statement and ??= assigns 10 to it.
   }
   ```

   

**Ternary Operator:**

Similar to ternary operator in other languages like  C++



**is operator:**

we can check a variable datatype using ``is`` operator.

```dart
main(){
    int x = 10;
    if(x is int){
        print("x is integer data type\n");
    }
}
```



> **nested if and switch statements are similar in other languages like c++.**



## Loops

### for loop

```dart
for (int i=0;i<n;i++){
    print("I am in a for loop $i");
}
```

```dart
var arr = [1,2,3];

for (var i: arr){
    print(i);
}
```

```dart
//this is similar to javascript

var arr = [1,2,3];

arr.forEach( (i) => {
    print(i)    
});

//this is like for every time we store the current cursor value in 'i' i.e, similar to for(var i:arr) loop but here '=>{}' represents a function as in javascript.

//notice no semicolon for print(i)
```

### while loop

```dart
while(i<n){
    print("I am in a for loop $i");
}
```

### do while loop:

```dart
int i = 10;
do{
    print(i);
    i -= 1;
}while(i >= 0);
```

>There are statements like ```break``` and ```continue``` as in c++ for managing the loop.



## Data Structures

### Lists:

```dart
main(){
	List arr = [1,2,3,4,5];
    for(int i:arr)
        print(i);
}

main(){
	List<int> arr = [1,2,3,4,5];
    for(var i in arr)
        print(i);
}

//both are valid
```

```dart
main(){
	List arr = [1,2,3,4,5,3.2];
    for(var i in arr)
        print(i);
}

//we can store any type of data type if we just use List and if we specify like in the previous example we need to follow it.
```

> size = arr.length // gives the length if array
>
> we can also change values after declaration



**Copying 2 lists:**

```dart
List<int> arr = [1,2,3];
var other = arr;

for(var i in other){
    print(i); //prints 1 2 3 (in different lines though)
}

//doing this is like referencing the same list also with another name 'other' here i.e, if we change any value in 'arr' it also reflects in 'other'
```

```dart
List<int> arr = [1,2,3];

//this just copies the values so any change in arr doesn't reflect in 'other' list
var other = [...arr]; 

for(var i in other){
    print(i); //prints 1 2 3 (in different lines though)
}
```



### Sets:

```dart
main(){
    var st = {1,2,3,1,4};
    for (var i in st){
        print(i);
    }
    
    // prints all unique values in the set st
}
```

**empty set?**

```dart
main(){
    var temp = {};
    print(temp.runtimeType);
    //prints hashmap instead of set
    
    var t = <int>{};
    print(t.runtimeType);
    //prints hashset
    
    Set<int> st = {};
    print(st.runtimeType);
    //prints hashset
}
```

### maps:

```dart
main(){
	var mp = {
        //key  :  value
        'name': 'akshith',
        'branch': 'ece',
        'batch': '2018-2022',
        1: 'we can also use like this'
    };
    
    print(mp['name']);
    print(mp[1]);
}
```

```dart
main(){
    var mp = Map();
    mp['name'] = 'akshith';
    
    //this is also a valid syntax
}
```



## functions:

Beauty of functions in dart is the ability of dart to change the datatype of a function dynamically.

```dart
void main(){
    print(square(5));
    print(square(5.5));
     
    //above is valid as the return type of square function is dynamic
}


dynamic square(var num){
    return (num * num);
}
```

> if return type of a function is void we can also avoid to mention it i.e,
>
> ```dart
> main(){
>     hello();
> }
> 
> hello(){
>     print("Hello World!");
> }
> ```
>
> **By observing above examples we can say that the location of the function doesn't matter.** 



**Array Function:**

If the function is having only one statement then we can simplify the syntax of the function as:

```dart
main(){
    hello();
}

hello() => print("Hello World!");
```

And also this works even for functions with some return type other than void also

```dart
void main(){
    print(square(5));
}


dynamic square(var num) => (num * num);

//in this case writing 'return' is not needed bcz it's the only line present so it must be return statement only.
```

**Anonymous Functions: **

Similar to Anonymous Functions in javascript here also we can do this eg:

```dart
main(){
    var arr = [1,2,3,4,5];
    
    arr.forEach((i) =>{
        print(i)
    });
}

// no semicolon near print statement
```



**Name parameters:**

By default the order of parameters (called ```positional parameters```) we pass to a function should be same as the order of parameters in the definition of it. If we don't want such then we can use this type of syntax also:

```dart
main(){
    print(sub(num2: 1,num1: 4));
}

dynamic sub({var num1, var num2}) => num1 - num2;

//this is also valid and it prints 3 (4-1 = 3) 
```

**Putting those flower brackets makes the parameters as name parameters and also makes them optional i.e, it's not required to pass all name parameters compulsorily.**



**Hybrid of positional parameters and Name parameters:**

```dart
main(){
    print(sum(1, num2:2));
}

dynamic sum(var num1, {var num2}) => num1 + num2;
```

```dart
main(){
    print(sum(10)); //valid
}

dynamic sum(var num1, {var num2}) => num1 + num2;

//accessing num2 in the function is not valid as it's not passed so we can give it a default value as:

//checks if num2 is null then returns only with num1
dynamic sum(var num1, {var num2}) => num1 + (num2 ?? 0) ;

//we can do the above defining default value with this syntax also:
dynamic sum(var num1, {var num2=0}) => num1 + num2;
```



**Misc:**

```dart
main(){
    print(sum(2,2));
    print(sum(10));
}

dynamic sum(var num1, [var num2]) => num1 + (num2 ?? 0);
```

**we can also make positional parameters optional by enclosing them between square brackets**







