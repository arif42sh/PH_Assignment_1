# B8A1 - TypeScript & OOP Assignment

This repository contains solutions for Assignment 1 of Apollo Level 2 Web Development, demonstrating core TypeScript concepts and Object-Oriented Programming (OOP).

## Project Structure

```text
├── solutions.ts
├── type-vs-interface.md
├── type-narrowing.md
└── README.md
```

## Problem Solving Overview (`solutions.ts`)

All problem solutions are implemented in `solutions.ts` strictly following explicit parameter and return typing, without using `any`:

1. **`multiplyValue`**: Handles multiplying numbers with optional parameters and proper `0` evaluation.
2. **`processInput`**: Type narrowing for `string | number | boolean` union types using `typeof`.
3. **`formatCoordinate`**: Readonly tuple formatting without mutability.
4. **`concatenateArrays`**: Generic function concatenating variable arrays using rest parameters.
5. **`Course` & `getPopularCourses`**: Interface definition and non-mutating filtering logic.
6. **`pluckValues`**: Generic property value extraction using the `keyof` constraint.
7. **`Employee` & `Manager`**: OOP classes demonstrating `protected` and `private` access modifiers and inheritance.
8. **`validateAgeAsync`**: Asynchronous age validation utilizing Promises, timeouts, and Error rejections.

## Blog Posts

- [Core Differences between Type Aliases and Interfaces](type-vs-interface.md)
- [Understanding Type Narrowing in TypeScript](type-narrowing.md)

