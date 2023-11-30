## Documentation

# 6 Rules of clean code 

1. Use meaningful names - Making use of meaningful variable, class, and method names makes code much more readable, allowing others to pick up your code and understand it quicker than if they were given vague or non-descript names.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation3.PNG)

While the above name may be meaningful, it is also shared with methods of the same name in other view pages, which may cause confusion. To correct this the code would be renamed to "RoomSaved". This avoids the confusion the code may have provied beforehand. It also explains the task the method performs following general method name convention.


2. Functions - There are general rules to follow when creating functions. Ideally functions should: have verb names; be short; have a small number of parameters; do one task; lack side effects; and be of a single level of abstraction. By following most of these principles you can create functions that are easy to maintain in large codebases without needing to change one long function that handled a task that it should have divided up.

The above code also shows how my naming could have been improved, however the the small number of parameters and the shortness of the function speak for its quality.



3. Comments - Making use of comments can provide greater insight into how to use a piece of code or understanding what it does. Some argue that too much commenting actually diminishes the value of the code and makes it less clean and so comments are best kept small while code should be improved to be more readable.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation4.PNG)

The code shown above is lacking in comments which may confuse people when they try to understand where the parameter e comes.
By adding comments above the code we could better explain that the parameter e is the reference to the Collection of Rooms from the XAML view, used to get which Room was selected for use in other methods.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation5.PNG)



4. DRY (Don't repeat yourself) - Preventing repeating code means there is less code to look through and manage and makes implementing changes easier (since you dont need to wander the code looking for multiple of the same task).

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation6.PNG)

The code above initializes the view page and assings needed variables. However it also loades the Rooms for the Collection displayed twice. This is not needed and so an easy fix is to remove the assignment for assignment source so that the load method handles it.


5. Single Responsibility Principle - By keeping classes and methods to a single responsibility and all code that forms a single responsibility should be grouped together. 

The above image also violates this principle by trying to handle the loading of the Collection since this is already handled by another method. If we reinitialized the page each time we wanted to update the view it would be a waste of resources and more confusing to code with.



6. KISS (Keep it simple, stupid) - By making the code understandable even after a long time has passed, you make it easier to understand and come back to without the need to reread documentation or experiment with it again.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation7.PNG)

The code above may seem fairly simple but if I were to return to this code after a long period of time I would have very little understanding of what RoomName actaully represents - perhaps a specific room like someone's bedroom? Or maybe a type of room like a gym? This can be improved using comments to explain the small bit of complexity within the code. Alternatively the attribute could be renamed to something more desciptive like RoomType.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation8.PNG)



# Doxygen

Doxygen is a handy tool for gathering and providing documentation for your code that makes it easier for others to take advantage of it and build upon it. It lets you explain the uses of classes and methods, their inputs, returns, what they represent and more. Even allowing you to link to other classes or references.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation10.PNG)

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation11.PNG)

As seen above, these are placed onto annotated HTML that groups your code together to make it easier to understand how they work together and displays it inside a simplified and summarised menu.
The above code is further explained by telling the user what gets returned by the code though it could certainly be better explained by evaluating where the rooms come from or what the typing is.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation11.PNG)

Though another use would be to further explain a parameter, such as in the code above. In this the parameter e is not well named and so the user has no idea what it represents. This could be better named but even if it wasnt doxy comments would be useful to explain where it retrieves the parameter from (in this case from the XAML collection).


# Avoiding Comments

When coding well, ideally your code should not need comments to explain how it works or what it does. To provide such an example I have the code behind saving a room:

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation1.PNG)

The names given to the methods and variables provide an understanding of what they provide. SaveRoom handles saving of a room to the database. LoadRoom handles the ensuring the Collection of Rooms holds all our Rooms. The method makes use of a small number of parameters, and it also only performs one task (handling the event when the save button is pressed). The code is also kept well layed-out and simple to understand.


Another example of clean code would be the Delete room:

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation2.PNG)

This code handles the event where the delete button is pressed on the RoomPage view. Because of the well named variables it is easy to tell that the first lines are checking if we have selected a room on the view menu, in such a case we haven't then the code ends there.
We also hand off appropriate tasks to other classes and other methods, such as handling removal from the database which is performed by the sevice class, or loading rooms being left to the LoadRooms method so we dont repeat code, leaving this method with one task. 


My last example is the XAML code for the RoomView page:

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Documentation/Documentation2.PNG)

Every reference to our methods and constants (such as the spacing and thickness) are named to be easy to understand. The use of constants also allows consistency between multiple pages.
The easy to understand method references like "DeleteRoom" clearly tell us their function. Additionally the names of the XAML objects such as "RoomListView" also are easy to understand.


This section is related to your work on clean code and documentation in week 5.

First, choose six rules of clean code and explain them. For each one,

* Summarise the rule in your own words.
* Provide an example from the code that you wrote in week 2 and then refined in week 4.
* Explain how your code implements the rule. 

Second, copy the doxygen comments from your code into your portfolio and provide some
descriptive commentary on their purpose and structure. Use screenshots showing the HTML 
content that is generated from your code to illustrate your explanation.

Finally, highlight three examples from your code where you have eliminated the need
for comments by adhering to the principles of clean code.
 
