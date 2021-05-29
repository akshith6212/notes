# JavaScript Course



## Intro to JavaScript



### JavaScript Document Object Model:

Document Object Model consists of nodes like:

- Element nodes: Here, the tags are called the element nodes
- Attribute Nodes: Attributes present in the tags are called attribute Nodes.
- Text Nodes: The actual content between an opening tag and a closing tag is called text node.

![DOM View](/home/akshith/Pictures/Screenshot from 2021-05-29 21-54-35.png)



### Data types in JavaScript:

![](/home/akshith/Pictures/Screenshot from 2021-05-29 22-01-36.png)



- JavaScript runs code line by line i.e, after running the first line it goes on to the other lines below the first line.

### JavaScript as a two props:

- JavaScript is a loosely typed language.
- JavaScript is also a dynamically typed language
  - Meaning to above statements is :
  - we can create a variable without declaring the variable type
    - Eg:           var a = 5;
    - ​                var b = "hello" 
  - Both the examples are valid and+ we can see that we are not declaring the type variable it is. This explains that JavaScript is a loosely typed language.
  - Coming to dynamically typed language:
    - Eg:           var a = 5;
    - ​                var a = "hello" 
  - Above example is also valid and we can see that here variable 'a' is both an integer as well as a string hence JavaScript is a dynamically typed language.



- *If else and loops are as similar to the other languages*



**JavaScript treats the whole HTML as document so, in order to get anything from the HTML blocks or post anything to the HTML we need to *document.* statement to access the nodes.**

**Eg: *document.write(" < h2 >Hello world</ h2> ");* inserts the HTML code into the actual HTML.**



### Syntax of some basic statements:

- **var** variable_name;  or simply *var_name = 5;*
- **if**(/* condition here */) {/ * code here * /} **else** { /*  code here */ }
- **switch (variable)** {/* cases here */}
  - Here the important one is that **variable passed to switch statement can be a integer, string, bool**
- **function** name(/* inputs here */){/* code here */}



### Associativity:

- JavaScript is evaluated from left to right while doing arithmetic operations having same operators.
- When having different operators we use BODMAS rule to evaluate.
- **Important point here is result = 6+9+"hello"+9+1; will be result = "15hello91"**
  - What happening here is as the associativity is from left to right JavaScript evaluates the integers and later on there is a string so it treates the later on variables as string and does concatenation.

### Scopes:

- As normal to other programming languages the scope is same here.
- **Variables declared by simply assigning value to them are by default global and some browsers don't restrict this type.**



### Arrays 

- **Arrays here are dynamic in nature** like vectors in c++. so, we can also push new elements after creating an array.
  - Eg: var arr = [1,2,3];
  - arr.push(4);

- Above is valid and the array *arr* will be [1,2,3,4].



## OOPS

