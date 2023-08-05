# Inline Function Type Annotation

```typescript
let mySum: (a: number, b: number) => number;

mySum = (a, b) => {
  return a + b;
};

console.log(mySum(1, 2)); // 3
```

# Type Alias for Function Type

```typescript
type sum = (a: number, b: number, type?: string) => number | string;

const mySum: sum = (a, b, type) => {
  if (type === "plus") {
    return a + b;
  } else {
    return Math.abs(Math.ceil(a - b));
  }
};

console.log(mySum(1.8, 9.1)); // 7

/// <========================================> ///

const myMultiply: sum = (a, b, type) => {
  return type + " = " + a * b;
};

console.log(mySum(1.8, 9.1));

console.log(myMultiply(52, 9, "multiply")); // multiply = 468
```

# Interface for Function Type

```typescript
interface User {
  (
    name: string,
    age: number,
    admin: boolean,
    address?: string,
    ...subject: string[]
  ): {
    name: string;
    age: number;
    admin: boolean;
    country: string;
    address?: string;
    subject?: string[];
  };
}

const user: User = (name, age, admin, address, ...subject) => {
  return { name, age, admin, address, country: "Bangladesh", subject };
};

console.log(
  user("Shatya Ranjon Sharma", 21, true, undefined, "c++", "java", "python")
);

/*
    {
        address:undefine,
        name:"Satya Ranjon Sharma",
        admin:true,
        age:21,
        country:"Bangladesh",
        subject:["c++","java","python]
    }
*/
```
