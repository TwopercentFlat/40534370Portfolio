## Testing

# Example 1

Using test cases can be a great way to make sure code remains working after many changes are made to a code base. The best way to test something is ensure that methods of classes perform their assigned tasks and testing it against various possibilities so that there are no cases where we get an unexpected outcome.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Testing/Testing1.PNG)

The above example shows the test for checking the DeleteAsync method works with the room model provided to it. To test it we connect to a test database and add a room to it. Afterwards we test the method by attempting to remove the room from the database. We check to make sure that the database has no rooms stored in it. If this wasn't tested then we wouldn't know if data could actaully be removed from the database sucessfully, meaning that it is not fit for purpose and does not meet the DoD.

# What Could be Improved

However this code could be improved by introducing another test that ensures when we have multiple entires in the databse that only the room we want to delete is removed. Or that the code doesn't break if the database is empty. Which it would most certainly do.

# Example 2

But to ensure that the code interacting with our database works we also need to test the ability to add entries into the database.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Testing/Testing2.PNG)

This code is designed to test that the data is sucessfully added into the database. First we prepare the database with roomService. Then we create a new room object to be added. Once added to the database we load from the database and check that the the roomName is correctly added and that it is the only instance of a room in the database. If this test had failed then we would know that there is a problem with adding rooms to the database meaning that the room object would almost be comepletly unusable and thus not fit for purpose as in our DoD.

# What Could be Improved

However this code could be improved. The room list is loaded twice when we only need to load after adding the new entry. addtionally since we are connected to a test database if data is left in future tests then this may disrupt the testing and give false fails. This could be corrected by making the program remove all entries in the database after testing finishes, or even on start.