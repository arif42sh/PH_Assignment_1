# Understanding Type Narrowing in TypeScript

## Introduction
In TypeScript, applications frequently work with union types where a variable can hold multiple potential data types. Type narrowing is the process of inspecting that variable at runtime so TypeScript can deduce its specific type within a conditional code block.

## How Type Narrowing Works

TypeScript evaluates runtime JavaScript control flow guards during compilation. The three most common ways to narrow types include:

### 1. Using `typeof`
For primitive types such as string, number, or boolean, the `typeof` operator provides straightforward type discrimination:

```ts
function printId(id: string | number) {
  if (typeof id === "string") {
    console.log(id.toUpperCase());
  } else {
    console.log(id * 2);
  }
}
```

Inside the `if` block, TypeScript recognizes `id` as a string, enabling string methods safely without runtime exceptions.

### 2. Using `instanceof`
When working with class instances or standard JavaScript objects like `Date` or `Error`, `instanceof` verifies the object prototype chain:

```ts
function logDate(value: Date | string) {
  if (value instanceof Date) {
    console.log(value.getFullYear());
  } else {
    console.log(new Date(value).getFullYear());
  }
}
```

### 3. Using the `in` Operator
To differentiate between distinct object shapes, the `in` operator checks whether a specific property exists:

```ts
type Car = { drive: () => void };
type Boat = { sail: () => void };

function operateVehicle(vehicle: Car | Boat) {
  if ("drive" in vehicle) {
    vehicle.drive();
  } else {
    vehicle.sail();
  }
}
```

## Conclusion
Type narrowing makes TypeScript code both flexible and strictly type-safe. Instead of relying on unsafe type casting assertions (`as`), narrowing allows TypeScript to follow standard JavaScript runtime logic cleanly and reliably.
