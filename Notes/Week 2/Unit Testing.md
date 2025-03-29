
​Unit testing is a crucial aspect of software development, ensuring that individual components of an application function correctly in isolation.

**most utilized JavaScript unit testing frameworks include:**
1. **Jest**: Developed by Facebook, Jest is renowned for its ease of use, speed, and built-in functionalities, making it a preferred choice for many developers.​
- **Mocha**: A flexible testing framework that provides developers with a choice of assertion libraries and other tools, allowing for a customizable testing environment.
- **Jasmine**: A behavior-driven development framework that offers a clean syntax and comes with a built-in assertion library, enabling straightforward test writing.​[CodeFlex Automation](https://www.testim.io/blog/angular-unit-testing-get-started/?utm_source=chatgpt.com)
- **Karma**: Primarily a test runner, Karma allows developers to execute tests across multiple real browsers, ensuring compatibility and reliability.​
- **AVA**: A minimalistic framework that emphasizes speed and simplicity, supporting concurrent test execution to optimize performance.
- Vitest
- React testing library
- Enzyme
- Story Book

###### Types
1. Manual Testing 
2. Automation Testing
Different type of Testing 
	1. **Unit testing:** Testing a Unit of code
	2.  **Integration Testing**: Testing with a compination of components
	3. **End- end Testing (E2E)**: Testing visualy just like how the user  Intracts
###### Most common syntax
	- describe()
	- it()
	- test()

>[!info]
>Folder name: **__tests__** 
>Filename:**Botton.test.jsx**
>



#### Vitest


- describe enna syntax 2 parameteres edukkum one  the name of function which we want tesr second a callback
```
describe("add",()=>{})
```
add enno enth vennelum nalkam ("tesing code of add function")
ithinull we can add **it** or **test**
- it um describe pole thanne anne
``` 
  it("return 1+1 =2",()=>{
        expect(add(10,10)).toBe(20);
    })
```
- here we will add expect which is import from vitest
- here **add** is our function after the **.toBe** what we will expect
