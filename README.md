# Object-Oriented Programming (OOP) in JavaScript

Object-Oriented Programming (OOP) is a programming paradigm centered around objects, which are collections of properties and methods. JavaScript, being a versatile language, supports OOP through different approaches, including object literals, constructor functions, prototypes, and ES6 classes.

## Why Use OOP?
OOP provides a structured approach to programming, making code reusable, scalable, and easier to maintain. The key benefits include:
- **Code Reusability**: Use the same code across different parts of the application.
- **Encapsulation**: Keep related data and functions together.
- **Inheritance**: Share functionality between objects.
- **Abstraction**: Hide unnecessary details from the user.
- **Polymorphism**: Use a single interface for multiple data types.

## Parts of OOP in JavaScript

### 1. Object Literal
Objects in JavaScript can be created using object literals. This is a simple and direct way to define an object with properties and methods.
```javascript
const person = {
    name: "Hamza",
    age: 25,
    greet: function() {
        console.log("Hello, " + this.name);
    }
};
person.greet(); // Output: Hello, Hamza
```

### 2. Constructor Function
A constructor function is a blueprint for creating objects. It uses the `this` keyword to assign properties and is called using the `new` keyword.
```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.greet = function() {
        console.log("Hello, " + this.name);
    };
}
const user = new Person("Hamza", 25);
user.greet(); // Output: Hello, Hamza
```

### 3. Prototypes
In JavaScript, every function has a `prototype` property that allows adding methods that can be shared across all instances.
```javascript
Person.prototype.sayAge = function() {
    console.log("I am " + this.age + " years old.");
};
user.sayAge(); // Output: I am 25 years old.
```

### 4. Classes (ES6)
ES6 introduced classes, making OOP implementation more readable and structured.
```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    greet() {
        console.log("Hello, " + this.name);
    }
}
const user2 = new Person("Ali", 30);
user2.greet(); // Output: Hello, Ali
```

### 5. Instances (`new`, `this`)
An instance is an object created from a class or constructor function using the `new` keyword.
```javascript
const anotherUser = new Person("Ahmed", 28);
anotherUser.greet(); // Output: Hello, Ahmed
```

## The 4 Pillars of OOP

### 1. Abstraction
Hiding implementation details and exposing only necessary features.
```javascript
class Car {
    constructor(model) {
        this.model = model;
    }
    start() {
        console.log("Engine started!");
    }
}
const myCar = new Car("Toyota");
myCar.start(); // Output: Engine started!
```

### 2. Encapsulation
Bundling data and methods together to prevent direct access to certain properties.
```javascript
class BankAccount {
    constructor(balance) {
        let _balance = balance; // Private variable
        this.getBalance = function() {
            return _balance;
        };
    }
}
const account = new BankAccount(1000);
console.log(account.getBalance()); // Output: 1000
```

### 3. Inheritance
Allowing a class to inherit properties and methods from another class.
```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
    makeSound() {
        console.log("Some sound");
    }
}
class Dog extends Animal {
    makeSound() {
        console.log("Bark");
    }
}
const myDog = new Dog("Buddy");
myDog.makeSound(); // Output: Bark
```

### 4. Polymorphism
Using the same method name for different types of objects.
```javascript
class Shape {
    draw() {
        console.log("Drawing a shape");
    }
}
class Circle extends Shape {
    draw() {
        console.log("Drawing a circle");
    }
}
const myShape = new Circle();
myShape.draw(); // Output: Drawing a circle
```

## Conclusion
Object-Oriented Programming in JavaScript provides a robust way to structure code, making it more efficient and maintainable. Understanding concepts like objects, classes, prototypes, and the four pillars of OOP will help you write better and more scalable JavaScript applications.