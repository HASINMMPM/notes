
```
// Using interface
interface User {
  name: string;
  age: number;
}

// Using type
type User = {
  name: string;
  age: number;
};

```

- **Interface**: Can be extended using `extends`.
- **type**: Can extend via intersections (`&`).

```
// interface
interface Person {
  name: string;
}
interface Employee extends Person {
  salary: number;
}

// type
type Person = { name: string };
type Employee = Person & { salary: number };

```

- **Declaration Merging** Only **interface** supports this feature:
```interface User {
  name: string;
}
interface User {
  age: number;
}
// Merged into: { name: string, age: number }

//`type` cannot do this. It will throw an error if you try to redefine it.
```
