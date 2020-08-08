# Report

### Summary
Codebase refactoring to include SOLID principles.
The original project codebase is difficult to manage due to lack of SOLID principles.
In Object Oriented Programming, SOLID is a short form for five design principles which helps make software design easy to understand, maintain and edit.

### Description
The original project codebase is difficult to manage due to lack of **S.O.L.I.D principles**.
SOLID stands for:
* **S**ingle responsibility
* **O**pen-closed
* **L**iskov substitution
* **I**nterface segregation
* **D**ependency inversion.

#### Single Responsibility
Each class should be designed in a way that it handles only responsibility. This helps in having less side effects when changes to original code are made.
*Example:*
```
class EmployeeManagement
{
	public static void main(String args[])
	{
		//Code to take employee details as input
		//Code to add details to database
	}
}
```

Instead, two separate classes can be used:
```
class EmployeeManagement
{
	//Code to take employee details as input
	//Calls appropriate function of other class to add details to databse
}

class EmployeeDao
{
	//Code to add details to databse
}
```

#### Open-Closed Principle
Classes used in codebase should be designed in such a way that adding extra feature can be achieved by extending the class and there’s no need to modify original class.

*Example:*
```
class Employee
{
	//Code to take employee details as input
}

class Managers extends Employee
{
	//Code to add additional details
}
```

#### Liskov Substitution Principle
This states that derived classes must be substitutable for their base classes. This means, if B is derived class and A is base class; the program should work exactly same irrespective of which object is used.

*Example:*
```
class Employee
{
	//Code to print employee details
}

class Manager extends Employee
{
	//Code to print manager details
}
```
Here, classes should be designed in such a way that enables same behaviour irrespective of the object with which function is invoked

#### Interface Segregation Principle
Just like classes, interfaces should be designed in a way which allows clients who implements the interface to not depend upon methods which are not required by client.
*Example:*
```
class Employee
{

}

class TechTeam extends Employee
{

}

class SalesTeam extends Employee
{

}
```
#### Dependency Inversion
Classes should depend upon abstractions and not concrete details from another class.

References:
[Wikipedia](https://en.wikipedia.org/wiki/SOLID)
[The Team Coder](https://team-coder.com/solid-principles/)
[TechBeacon](https://techbeacon.com/app-dev-testing/how-write-effective-software-defect-reports)
