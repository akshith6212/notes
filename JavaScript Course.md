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
    - ```javascript
      Eg: var a = 5;
      ```
    
    - ```javascript
      var b = "hello";                 
      ```
  - Both the examples are valid and+ we can see that we are not declaring the type variable it is. This explains that JavaScript is a loosely typed language.
  - Coming to dynamically typed language:
    - ```javascript
      Eg:  var a = 5;
      ```
    
    - ```javascript
      var a = "hello"; 
      ```
  - Above example is also valid and we can see that here variable 'a' is both an integer as well as a string hence JavaScript is a dynamically typed language.



- *If else and loops are as similar to the other languages*



**JavaScript treats the whole HTML as document so, in order to get anything from the HTML blocks or post anything to the HTML we need to *document.* statement to access the nodes.**

**Eg: *document.write(" < h2 >Hello world</ h2> ");* inserts the HTML code into the actual HTML.**



### Syntax of some basic statements:

- ```  javascript
  var variable_name;  or simply var_name = 5;
  ```

- ``` javascript
  if(/* condition(s) here */) {/* code here */} else { /*  code here */ }
  ```

- ```javascript
  switch (variable) {/* cases here */}
  ```
  
  - Here the important one is that **variable passed to switch statement can be a integer, string, bool**
  
- ```javascript
  function name(/* inputs here */){/* code here */}
  ```



### Associativity:

- JavaScript is evaluated from left to right while doing arithmetic operations having same operators.
- When having different operators we use BODMAS rule to evaluate.
- **Important point here is result = 6+9+"hello"+9+1; will be result = "15hello91"**
  - What happening here is as the associativity is from left to right JavaScript evaluates the integers and later on there is a string so it treats the later on variables as string and does concatenation.

### Scopes:

- As normal to other programming languages the scope is same here.
- **Variables declared by simply assigning value to them are by default global and some browsers don't restrict this type.**



### Arrays 

- **Arrays here are dynamic in nature** like vectors in c++. so, we can also push new elements after creating an array.
  - ``` javascript
    Eg:  var arr = [1,2,3];
    ```
  
  -  ``` javascript
     arr.push(4);
     ```
  
- Above is valid and the array *arr* will be [1,2,3,4].



## OOPS

### Objects

Eg: Below is a example of an object

```javascript
var car{
    
	car_brand: "Tesla",
	car_model: "Model 3",
	price: 35000,
	teslaAutoPilot: function(){
		document.wrie("<h2> Tesla is a legend. </h2>");
	}
    
}
```

*From above car object we can access it's model name using car.car_model and price by car.price etc.....*



- We can also create objects of data types like integer, string, boolean by defining with the new keyword.

- ```javascript
  var str1 = new String();
  ```

- ```javascript
  str1.length // gives the length of string
  //Here, str1 is an object and if we create a variable like
  
  var str2 = "hello"; //Now, str2 is a string.
  ```

- We can also add other properties to the existing objects then we can also create it outside the object declaration like:

- ```javascript
  var car{
      
  	car_brand: "Tesla",
  	car_model: "Model 3",
  	price: 35000,
  	teslaAutoPilot: function(){
  		document.wrie("<h2> Tesla is a legend. </h2>");
  	}
      
  }
  
  car.fueltype = "Electric";
  
  //Now, car also has a property named fueltype => car.fueltype returns "Electric".
  ```

- Similarly we can also delete the properties like:

- ```javascript
  delete car.price; 
  ```



### **Function Constructors**

These are just like the constructors in the C++ classes where we pass the parameters to get an object.

**Example**:

```javascript
function car(car_brand, car_model, price){

	this.car_brand = car_brand;
    this.car_model = car_model;
    this.price = price;
    this.func(){
        document.write(<h2> Tesla is a Legend </h2>);
    }

}
```

Now create an object.

```javascript
var obj = new car('Tesla','Model B',35000);
```

**Now, we can access the variables like car_model etc.. using the dot(' . ') operator like ``` var price = obj.price; ```**



## DOM Manipulations

### Events using methods 

- ```javascript
  onclick = "func()" //is the attribute we need to give for this type of button events.
  ```

- ```javascript
  document.getElementById(/*id here*/); //returns the element node having the id passed
  ```

- ```javascript
  var str = document.getElementById("someheading"); 
  // Now, we can access the text node of this element using
  str.innerHTML; //gives the text node of the element node and we can also alter it using this.
  ```

- ```javascript
  /* Now, this */ document.getElementById();// returns only one object so if we want to change multiple objects then we use
  
  document.getElementsByTagName(); // and this returns a list of js objects having the same tagname passed.
  ```

- ```javascript
  /* Similarly as above we can also get the elements using classes by */ document.getElementsByClassName(); // and this returns a list of js objects having the same class passed.
  ```

- ```javascript
  /* Similarly as above we can also get the elements using classes by */ document.getElementsByName(); // and this returns a list of js objects having the same class passed.
  ```

  

**We can access the attributes and change them using the dot operator.**



### MOUSE Events:

- ```javascript
  onmouseover = "func()", onmouseout = "other_func()" 
  //are the attributes we need to give for this type of mouse events namely mouse hover function and mouse non hover functions.
  ```

  

### Form Validations:

- ```html
  <form>
     <!-- This tag is specifically used to submit/POST user inputs and we can't submit/POST without using it. This doesn't change the way the website looks but used for POST requests. --> 
  </form>
  
   <!-- Button needs to be a type of submit specifically -->
  ```

- ```html
  <script>
  	function validate(){
          var user = document.getElementById("username");
          var pass = document.getElementById("password");
          if (user.value.trim() == "" || pass.value.trim() = "") {
              alert("No Blank Values allowed");
              return false;
          } else {
              return true;
          }
      }
  </script>
  
  <form onsubmit="return validate()" action="page.html">
      <input id="username" type="text" placeholder="username"><br>
      <input id="password" type="password" placeholder="password"><br>
      <button type="submit" onclick="check()"> Submit </button>
  </form>
  ```

- The above HTML code takes input namely username and password and checks if it's not null and if  so, it redirects to "page.html". **Important thing here is the attribute of form tag onsubmit having return statement in the attribute value indicating the dynamic nature i.e, the attribute activates when the onsubmit attribute is true and it will become true iff and only iff the validate() function returns true. and if we remove the return statement in the onsubmit attribute value then it redirects independent of the boolean value returned by the validate() function.

- ```html
  // This form validates the username and password and indicate invalid entry iff any
  <script>
  	function validate(){
          var user = document.getElementById("username");
          var pass = document.getElementById("password");
          
          if (user.value.trim() == "") {
              alert("Blank Username");
              user.style.border = "solid 3px red"; // makes the border red indicating invalid entry
              document.getElementById("lbluser").style.visibility = "visible"; //A red label indicating invalid entry
              return false;
          } else if (pass.value.trim() = "") {
              alert("Blank Password");
              pass.style.border = "solid 3px red"; // makes the border red indicating invalid entry
              return false;
          } else if(pass.value.length < 5) {
              alert("Password minimum length is 5");
              return false;
          } else {
              return true;
          }
      }
  </script>
  
  <form onsubmit="return validate()" action="page.html">
      <input id="username" type="text" placeholder="username"><br>
      <label id="lbluser" style="color:red; visibility: hidden;">Invalid</label>
      <input id="password" type="password" placeholder="password"><br>
      <button type="submit" onclick="check()"> Submit </button>
  </form>
  ```

  

  

  

  ### **Regular Expressions:**

  **These are the expressions/patterns that are present in the usernames that are used to identify whether the username is valid or not.**

  ```html
  //In this we check whether the entered username is having specific patterns like our rollno startswith B18xxxxEC etc...
  
  //Here the postion of the regular expression is not concerned ut the content in the regualr expression is of the concern.
  
  <script>
  	function validate(){
          var user = document.getElementById("username").value;
          var regx = /B18/; //regular expression used for checking
          if (regx.test(user)) {
              alert("Valid Username");
              return true;
          } else {
              alert("Invalid Username");
              document.getElementById("lbluser").style.visibility = "visible"; //A red label indicating invalid entry
              return false;
          }
      }
  </script>
  
  <form onsubmit="return validate()" action="page.html">
      <input id="username" type="text" placeholder="username">
      <label id="lbluser" style="color:red; visibility: hidden;">Invalid</label><br>
      <button type="submit" onclick="check()"> Submit </button>
  </form>
  ```

  

- Specially here we have inbuilt functions to check the regular expressions like test() in the above example and for making the regular expression case insensitive i.e, not checking the case of the testing text we can use the syntax like: **/B18/i**. The 'i' here indicates the regular expression is case insensitive.

- Now, here we check the regular expression for more general cases like B18, B19 etc..

  ```html
  //In this we check whether the entered username is having specific patterns like our rollno startswith B18xxxxEC and also B19xxxxEC also.
  
  <script>
  	function validate(){
          var user = document.getElementById("username").value;
          var regx = /B1[89]/; //regular expression used for checking
          if (regx.test(user)) {
              alert("Valid Username");
              return true;
          } else {
              alert("Invalid Username");
              document.getElementById("lbluser").style.visibility = "visible"; //A red label indicating invalid entry
              return false;
          }
      }
  </script>
  
  <form onsubmit="return validate()" action="page.html">
      <input id="username" type="text" placeholder="username">
      <label id="lbluser" style="color:red; visibility: hidden;">Invalid</label><br>
      <button type="button" onclick="check()"> Submit </button>
  </form>
  ```

- Here, in regx = /B1[89]/; we are saying that the regular expression can also contain the B19 or B18 by indicating them in the square brackets giving a character set. We can also mention the range in the regular expression by something like: [a-x] meaning: the letter can be anything from a to x.
- If we want to exclude something in the regular expression we can indicate it by [ ^ *expression to exclude*] and here we can also indicate a range like [ ^ a-x] indicating we don't anything from a-x.
- 
