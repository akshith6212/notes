## Intro to jQuery library

This is a JavaScript **library** where the functions are pre-written and we are able to use it thus easing our work and it's compatible with all browsers.

### jQuery Selectors:

These allow you to select and manipulate the element nodes tn the HTML.

Example:

```html
<body>
    <h1>
        Welcome to jQuery
    </h1>
    <button onclick="func()" id="btn">
        Clickme
    </button>
</body>

<!-- this is jquery library access using CDN's -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

<!-- Now, using jQuery library functions below -->
<script>
	function func(){
        $("h1").fadeToggle(); //toggling using jQuery functions
    }
</script>

<!--- 
the syntax here is $("id/class/tag").action();
and the action() is any function in jQuery.
--->
```

- In above example ``` fadeToggle() ``` is a function for fading and we can pass time it takes to fade as parameter also like: ``` fadeToggle(2000) ``` meaning fade it for 2000ms => 2seconds.

- **We can also pass multiple classes/id's/tags in the $ selector like:** 

- ```html
  <body>
      <h1 id="h1">
          Welcome to jQuery.
      </h1>
      
      <div id="fp" class="mydivs">
          <p>
              This is first paragraph.
          </p>
      </div>
      
      <div id="sp" class="mydivs">
          <p>
              This is Second paragraph.
          </p>
      </div>
      
      <div id="tp" class="mydivs">
          <ul>
              <li>List1</li>
              <li>List2</li>
              <li>List3</li>
              <li>List4</li>
          </ul>
      </div>
      <button onclick="func()" id="btn">
          Clickme
      </button>
  </body>
  
  <!-- this is jquery library access using CDN's -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
  
  <!-- Now, using jQuery library functions below -->
  <script>
  	function func(){
          $("#fp,p,li").fadeToggle(); 
          //above will fadeaway the elements with id as fp and tags with p and li. Hence we can pass multiple id/tag/class
      }
  </script>
  
  ```

- Still to add is that we can also pass the id/class/tag as similar to css i.e, ``` $("div > p").fadeToggle(); ``` or ``` $("div p").fadeToggle(); ```  this will toggle only the paragraph tags under div tags 😉.

- Now, if we want to modify the properties i.e, apply js to first tags bearing specific tag/id/class then we can also do that by indicating ```:first``` after the tag/id/class similarly we can also add ```:even``` to modify properties of even numbered elements **Here, the numbering starts from 0** and similarly ```:odd```. Example: ```$("div:first").fadeToggle();``` hides the first div tag ``` $("div:even").fadeToggle(); ```  hides the even numbered div tags.

  

### Events from jQuery:

1. **click() event**

   - ```html
     <body>
         <h1 id="h1">
             Welcome to jQuery.
         </h1>
         
         <div id="fp" class="mydivs">
             <p>
                 This is first paragraph.
             </p>
         </div>
         
         <div id="sp" class="mydivs">
             <p>
                 This is Second paragraph.
             </p>
         </div>
         
         <div id="tp" class="mydivs">
             <ul>
                 <li>List1</li>
                 <li>List2</li>
                 <li>List3</li>
                 <li>List4</li>
             </ul>
         </div>
         <button id="btn">
             Clickme
         </button>
     </body>
     
     <!-- this is jquery library access using CDN's -->
     <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
     
     <!-- Now, using jQuery library functions below -->
     <script>
         $(document).ready(function(){ 
             //this loads only after the html document is loaded completely ensures misbehaviour
             
             //instead of giving the onclick attribute in HTML for the button we can also give it using js
             $("button").click(func);
             function func(){
                 $("#fp,p,li").fadeToggle(); 
             }
         });
     	
     </script>
     <!-- Above implementation or Below works -->
     <script>
         $(document).ready(function(){ 
             $("button").click(function(){
                 $("#fp,p,li").fadeToggle();  // define in the click event itself.
             } );
         });
     	
     </script>
     ```

2. **double click event => dblclick()**

   - This is similar to click() event but here, we need to click the button twice in order to trigger the function.

3. **mouseenter() and mouseleave() events simliar to hovering events**

   - ```html
     <body>
         <h1 id="h1">
             Welcome to jQuery.
         </h1>
         <button id="btn">
             Clickme
         </button>
     </body>
     
     <!-- this is jquery library access using CDN's -->
     <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
     
     <!-- Now, using jQuery library functions below -->
     <!-- using mouseenter() and mouseleave() -->
     <script>
         $(document).ready(function(){ 
             $("#btn").mouseenter(func1);//activated on hovering in 
             $("#btn").mouseleave(func1);//activated on hovering out
             function func1(){
                 $("h1").fadeOut(); 
             }
             function func2(){
                 $("h1").fadeIn(); 
             }
         });
     </script>
     <!-- using hover() function which is a combined version of mouseenter() and mouseleave() -->
     <script>
         $(document).ready(function(){ 
             $("#btn").hover(func1,func2);
             function func1(){
                 $("h1").fadeOut(); 
             }
             function func2(){
                 $("h1").fadeIn(); 
             }
         });
     </script>
     ```

     

### Effects:

1. **hide()**:
   - Used to hide some tag/id/class.

2. **show()**:
   - Used to unhide i.e, show the hided tag/id/class.

3. **toggle()**:
   - Used to do both hide() and show() using one single button.

Example:

```html
<body>
    <h1 id="h1">
        Welcome to jQuery.
    </h1>
    <button id="btn1">
        Hide
    </button>
    <button id="btn2">
        Show
    </button>
    <button id="btn3">
        Toggle
    </button>
</body>

<!-- this is jquery library access using CDN's -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

<!-- Now, using jQuery library functions below -->
<script>
    $(document).ready(function(){ 
        $("#btn1").click(function(){
            $("h1").hide();
        }) ;
        $("#btn2").click(function(){
            $("h1").show();
        }) ;
        $("#btn3").click(function(){
            $("h1").toggle();
        }) ;
    });
</script>
```

4. **fadeOut()**:
   - fades out the selected ones.
5. **fadeIn()**:
   -  fades in the selected ones.
6. **fadeToggle()**:
   - toggles out the selected ones.

Example:

```html
<body>
    <h1 id="h1">
        Welcome to jQuery.
    </h1>
    <button id="btn1">
        fadeout
    </button>
    <button id="btn2">
        fadein
    </button>
    <button id="btn3">
        Toggle
    </button>
</body>

<!-- this is jquery library access using CDN's -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js" integrity="sha512-894YE6QWD5I59HgZOGReFYm4dnWc1Qt5NtvYSaNcOP+u1T9qYdvdihz0PPSiiqn/+/3e7Jo4EaG7TubfWGUrMQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

<!-- Now, using jQuery library functions below -->
<script>
    $(document).ready(function(){ 
        $("#btn1").click(function(){
            $("h1").fadeOut();
        }) ;
        $("#btn2").click(function(){
            $("h1").fadeIn();
        }) ;
        $("#btn3").click(function(){
            $("h1").fadeToggle(); 
        }) ;
    });
</script>
```

7. **slideUp():**
   - Fades/hides by moving up.
8. **slideDown():**
   - Shows/unhides by moving down.
9. **slideToggle():**
   - Toggle b/w Hideing & Unhideing by moving up and down.

```html
<!-- Same body as above examples -->
<script>
    $(document).ready(function(){ 
        $("#btn1").click(function(){
            $("h1").slideUp();
        }) ;
        $("#btn2").click(function(){
            $("h1").slideDown();
        }) ;
        $("#btn3").click(function(){
            $("h1").slideToggle(); 
        }) ;
    });
</script>
```



### Animations:































