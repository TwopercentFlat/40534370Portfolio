## Code Review

# The Code

```C#
class HumanResources
 {
    static void Main(string[] args)
     {
         Person person = new Person();
         person = person.GetManager();
     }
 }
 
 class Person
 {
     public Department Department { get; set; }
     public Person GetManager()
     {
         return Department.GetManager();
     }
 }
 
 class Department
 {
     private readonly Person _manager;
     public Department(Person manager)
     {
         _manager = manager;
     }
     public Person GetManager()
     {
         return _manager;
     }
 }
```

# The Problem

Within this code there is a code smell. The middle man is a code smell in which a class' only job is to delegate its work to another class. In this case, the class Person's only task is to get the manager from department and return it to the client class HumanResources. This makes means the functionality of HumanResources is reliant on a Person having a manager, which could cause problems if we wanted a Manager who does not yet have staff below him.

# The Solution

To solve this problem we must either remove the Person class and implement the concept another way, or refactor the methods of the classes so that the client class HumanResources has direct access to the department rather than accessing it through the Person class. This is done by giving HumanResources a department (from the person's department) and using that to get the manager.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/CodeReview/CodeReview1.PNG)

```C#
class HumanResources
 {
    static void Main(string[] args)
     {
         Person person = new Person();
         Department department = person.getDepartment();
         person = department.GetManager();
     }
 }
 
 class Person
 {
     public Department Department { get; set; }
 }
 
 class Department
 {
     private readonly Person _manager;
     public Department(Person manager)
     {
         _manager = manager;
     }
     public Person GetManager()
     {
         return _manager;
     }
 }
```
# Why This Works

Now we don't make use of a specific person to get the manager meaning we avoid convoluted code. Say for example the code was thousands of lines long and we were forced to jump between multiple classes to access data. When a new person is trying to understand the code they will need to understand the internals of both classes to work with the code. This situation makes the code more prone to error when changes are needed later. Since this fix means a Person is not required to access a Department, if we ever needed to get the manager of a department we dont have the staff for, we can use the department to get the manager, avoiding errors that would otherwise occur.