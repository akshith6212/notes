# django 

- django is similar to mvc but it's mvt



# Create a new Project

- ``` bash
  django-admin startapp <name of the project>
  ```

## Running a django server

- ```bash
  cd <name of the project>
  ```

- ```bash
  python manage.py runserver #runs the server in localhost:8000
  ```

## Creating an app in the server

- ```bash
  python manage.py startapp <name of the app> #a folder is created
  ```




# Accepting Inputs from the user

We use the form tag to get it and in views.py following will be there:

```python
def add(request):
    val1 = int(request.POST['num1'])
    val2 = int(request.POST['num2'])
    # Both are values from the user 
    
    res = val1+val2
    # now use this result to print the answer in result.html page
    return render(request,'result.html',{'result':res})
	
#we use {} to send any inputs to the html page i.e, we can access these inputs in htmlpage
```

htmlpage:

```html
<form action="add" method="post"><!-- This action redirects the user to "add.html" here -->
    <input type="text" name="num1"> 
    <input type="text" name="num2">
    <input type="submit">
    <!-- This name attribute is used to get the value of the input in the views.py file -->
</form>
```





**If we want to go from one page to the other on a form submit then we need to use a token for csrf having the syntax {%csrf_token%}**. Just add this in the top of the starting of the form. 

Example:

```html
<form action="add" method="post"><!-- This action redirects the user to "add.html" here so we need to add a csrf token -->
    {% csrf_token %} <!-- This token says that the user hasn't come from an unknown page but came from a valid page. -->
    <input type="text" name="num1"> 
    <input type="text" name="num2">
    <input type="submit">
    <!-- This name attribute is used to get the value of the input in the views.py file -->
</form>
```



# Model View Template in django

Here, we separate models(data), logical part (depending on scenario we need to change i.e, logic) and layout(html).

so, here 

1. models.py deals with the data models i.e, the tables and columns in the database. 
2. views.py deals with the logic.
3. urls.py deals with the layout (what page we need to display now.....)



# Static Files

So for serving the static files django uses a separate folder for storing it . For using this we need to access it by {% static 'path of the file in static folder' %}