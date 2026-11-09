# Differences Between Type and Interface in TypeScript

## Introduction
When working with TypeScript, deciding between `type` and `interface` is one of the most common architectural considerations developers encounter. While both construct custom shapes for data structures, they behave differently under the hood and serve distinct purposes.

## Key Differences

The primary technical difference is **declaration merging**. When an `interface` is declared multiple times with the same identifier, TypeScript merges the declarations into a single definition automatically:

```ts
interface Developer {
  name: string;
}

interface Developer {
  role: string;
}
// Resulting Developer now contains both name and role
```

In contrast, attempting to re-declare a `type` alias with the same name triggers a compile-time duplicate identifier error. This auto-merging capability makes interfaces especially well-suited for building public libraries and extensible open APIs.

Another major distinction is versatility. A `type` alias can define primitive types, union types, and tuples directly:

```ts
type Role = "Admin" | "Editor" | "Viewer";
type Point = [number, number];
```

An `interface` cannot represent primitives or standalone unions; it is restricted to object structures and class contracts. 

Regarding inheritance, interfaces employ the `extends` keyword, which TypeScript optimizes internally during compilation. Conversely, type aliases compose types using intersection operators (`&`).

## Conclusion
In practice, choosing `interface` is ideal for modeling object structures, class contracts, and extensible application interfaces. Choosing `type` aliases is the natural choice when working with unions, primitives, tuples, or conditional type transformations.
