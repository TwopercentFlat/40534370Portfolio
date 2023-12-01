## Week 8 Work

# Code Quality

Creating the model and CRUD functions for the Building class to interact with the database as per DoD from task board.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Week8/Week8-1.PNG)

Following my work in the weeks prior my goal was to create this similar system like the Room task but following the things I have learned during the process and evaluation of the task. Taking lessons from when I first looked at clean code and made a PR request I had been requested to: simplify variable names and be more specific with them; add more doxygen comments; and change the return type of certain methods for better error handling among other things detailed here https://github.com/AloiSan/UndacBlue/pull/41

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Week8/Week8-2.PNG)

As can be seen here. The corrections made to the Room task also can be used here to make code cleaner and more effective. DRY and Good naming principles have been corrected. These fixes were also applied to the Room class and page in earlier weeks.


# Testing

Another improvement over the previous week is in regards to testing.
Previously the tests used were very limited, only checking the expected case from the functions but nothing else. So to improve this time I implemented more tests, these tests check for errors or unexpected outcomes which were not covered for the Room tests. 

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Week8/Week8-3.PNG)

In this example the first test covers our normal conditions. When we delete a database entry it should leave our database empty since it was the only entry. But what happens if a delete was called without anything in the database. In such a sitation we should be able to check that we got an error correctly. The 2nd test tells us that the task failed by returning a false boolean.

A similar change was made to the update test as shown below.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Week8/Week8-3.PNG)

For this test the function returns null on an unsuccessful attempt. This is a little inconsistent and could be corrected next week as part of changes made then. But the test does what it is intended to do. If we attempt to update an entry that no longer exists, then we should expect an error or at least nothing to happen. 


# Reviewing A PR

When asked to review another group member's PR I had picked up on a few issues that were important as well as a few minor ones.
Firstly, the pull destination - the pull destination was set to the Master branch which is a no-go, changes should be applied to the dev branch to keep the master branch clean, and only once dev branches are intergrated correctly and code has been revied should code be considered for commiting into the Master branch.

The following image also shows the absence of certain CRUD operations within the code. Therefore not meeting the DoD.
![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Week8/Week8-5.PNG)

Secondly inconsistent implementation - Our group had arranged a general class (Base Entity) that would implement most of the functions for every other class, which would inherit those functions for their own use. The PR was making use of MVVM still rather than our system and so I had requested changes the implementation to match more with the system afterwards.

Minor issues - Some variables were not clearly named, still using plain letter variables (x,y,z), and also having a lack of comments for more complex functions.


# Review and Self-Analysis

The reassignment of database variables during testing could be avoided by making use of Mock objects or a general class-wide variable to make tests quicker to run or greater in scope. And while testing could be performed on XAML elements and their relevant C# code I couldn't find a nice way to do so without large changes to the functions. Usually testing is done upon an interface or as part of intergration between elements and interfaces, especially with mock, which makes it difficult with the lack of interfaces in the code.

As for the problems within the team. A lack of communication between members can really slow down work especially early on when a general plan hasn't been established. Though after a layout or plan is established work can be picked up more independantly, and through proper documentation of code or accurate naming, working alongside other's code (like in the case of the base entity class) can be made easy. 


PR:
https://github.com/AloiSan/UndacBlue/pull/53