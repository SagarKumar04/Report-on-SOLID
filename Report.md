# Report

### Summary
Codebase refactoring to include SOLID principles.

### Description
The original project codebase is difficult to manage due to lack of **S.O.L.I.D principles**.
In Object Oriented Programming, S.O.L.I.D. is a short form for five design principles which helps make software design easy to understand, maintain and edit.
SOLID stands for:
* **S**ingle responsibility
* **O**pen-closed
* **L**iskov substitution
* **I**nterface segregation
* **D**ependency inversion

#### Single Responsibility
Each class should be designed in a way that it handles only one responsibility. This helps in having less side effects when changes to original code are made.
*Example:*
```
class EmployeeManagement {
	public static void main(String args[]) {
		//code to take employee details as input
		//code to add details to database
	}
}
```

Instead, two separate classes can be used:
```
class EmployeeManagement {
	//code to take employee details as input
	//calls appropriate function of other class to add details to databse
}

class EmployeeDao {
	//code to add details to databse
}
```

#### Open-Closed Principle
Classes used in codebase should be designed in a way such that adding extra feature(s) can be achieved by extending the class and there’s no need to modify original class.

*Example:*
```
class Employee {
	//business logic
}

class Managers extends Employee {
	//business logic
}
```

#### Liskov Substitution Principle
This states that derived classes must be substitutable for their base classes. This means, if B is derived class and A is base class; the program should work exactly same irrespective of which object is used.

*Example:*
```
class Employee {
	//business logic
}

class Manager extends Employee {
	//business logic
}
```
Here, classes should be designed in such a way that enables same behaviour irrespective of the object with which function is invoked.

#### Interface Segregation Principle
Interfaces should be designed in a way which allows clients who implements the interface to not depend upon methods which are not required by client.
*Example:*
```
class Employee {
	//appropriate data members and member functions
}

class TechTeam extends Employee {
	//appropriate data members and member functions
}

class SalesTeam extends Employee {
	//appropriate data members and member functions
}
```
#### Dependency Inversion
This says that, high level modules should not depend on low level modules. Both should depend on abstraction.
It also states that abstractions should not depend upon details, but details should depend upon abstraction.
*Example*
```
class Consumer {
	private Producer producer;
	
	public Consumer() {
		producer = new Producer();
	}
	
	//business logic
}

class Producer {
	//business logic
}
```
Here, _Consumer_ is dependent on _Producer_, which should not be the case so as to allow loose coupling and unit testing.
The solution is, to use an abstract layer -  interfaces.

Instead, we can create interface of _Consumer_ and implement the above code as follows:
```
interface ProducerInterface {
	//business logic
}

class Producer implements ProducerInterface {
	//business logic
}

class Consumer extends Producer {
	//business logic
}
```

References:
* [Wikipedia](https://en.wikipedia.org/wiki/SOLID)
* [The Team Coder](https://team-coder.com/solid-principles/)
* [TechBeacon](https://techbeacon.com/app-dev-testing/how-write-effective-software-defect-reports)
