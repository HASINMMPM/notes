
##### Encapsulation (Data Hiding)
Encapsulation means bundling data and methods within a class and restricting direct access to some of the object's properties.

```
class Person {
  #age; // Private property (using # makes it inaccessible outside the class)

  constructor(name, age) {
    this.name = name;
    this.#age = age;
  }

  getAge() { // Public method to access private property
    return this.#age;
  }

  setAge(newAge) { // Public method to modify private property
    if (newAge > 0) {
      this.#age = newAge;
    } else {
      console.log("Age must be positive!");
    }
  }
}

const person = new Person("Alice", 25);
console.log(person.name);  // ✅ Accessible
console.log(person.getAge()); // ✅ Accessible via method
// console.log(person.#age); // ❌ Error: Private field cannot be accessed directly

person.setAge(30); 
console.log(person.getAge()); // Updated age: 30

```

>[!info]
>age ne direct call cheyyan pattilla function vech Vennam call cheyyan
>**Why Encapsulation?** It prevents direct modification of data, ensuring better security and control.

----
##### Abstraction (Hiding Implementation Details)
Abstraction means exposing only necessary details and hiding the implementation.

```
class Car {
  constructor(brand) {
    this.brand = brand;
  }

  start() {
    console.log(`${this.brand} is starting...`);
    this.#fuelInjection(); // Private method called inside public method
  }

  #fuelInjection() { // Private method, can't be accessed outside the class
    console.log("Injecting fuel...");
  }
}

const myCar = new Car("Tesla");
myCar.start(); // Tesla is starting... Injecting fuel...
// myCar.#fuelInjection(); // ❌ Error: Private method not accessible

```
>[!info]
>**Why Abstraction?** It simplifies usage by hiding complex details from the user.
>**# ith** koduthal athine classinullille functions le call cheyyam ennit aa function ne out le call cheyyam

avashyamaya details users ne return cheyyunnu mattullava hidding cheyyunnu. **EG:** Work of remote and Tv

---

##### Inheritance (Reusing Code)
Inheritance allows a class to derive properties and methods from another class.

```
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

// Dog class inherits from Animal
class Dog extends Animal {
  speak() { // Method overriding
    console.log(`${this.name} barks.`);
  }
}

const myDog = new Dog("Buddy");
myDog.speak(); // Output: Buddy barks.

```
>[!info]
>**Why Inheritance?** It avoids duplicate code and promotes reusability.

parent class ne superclass base class ennnum child class ne derived class ,extended class, subclass ennum ariyappedunnu

---

##### Polymorphism (Same Method, Different Behavior)
Polymorphism allows methods to have different behaviors based on the object that calls them.

```
class Shape {
  area() {
    console.log("Area calculation not defined.");
  }
}

class Circle extends Shape {
  constructor(radius) {
    super();
    this.radius = radius;
  }

  area() {
    return Math.PI * this.radius * this.radius;
  }
}

class Square extends Shape {
  constructor(side) {
    super();
    this.side = side;
  }

  area() {
    return this.side * this.side;
  }
}

const shapes = [new Circle(5), new Square(4)];

shapes.forEach(shape => console.log(shape.area())); 
// Circle: 78.54, Square: 16

```
>[!info]
>**Why Polymorphism?** It allows the same interface (`area()`) to be used for different behaviors.
>###### The `super()` method is used in **inheritance** when a child class wants to call the constructor of its parent class. It helps initialize the parent class's properties inside the child class.

Using in method overloading and method overriding 
**method overloading** ennal same name ulla multiple method call cheyyuka in a single class
**method overriding** extend cheytha onnil ninne parent class le mattam varuthuka


---
