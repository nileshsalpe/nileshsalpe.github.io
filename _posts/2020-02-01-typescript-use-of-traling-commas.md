---
layout: post
title: Use Of Trailing Commas In Typescript
categories: typescript javascript trailing-comma style formatter
---
# Use Of Trailing Commas In Typescript

## Table of Content
- [What is typescript](#what-is-typescript)
- [What is a trailing comma and why does it matter in typescript](#what-is-a-trailing-comma-and-why-does-it-matter-in-typescript)
- [What are the advantages of using trailing commas](#what-are-the-advantages-of-using-trailing-commas)
- [What are the disadvantages of using trailing commas](#what-are-the-disadvantages-of-using-trailing-commas)
- [References](#references)


## What is typescript?

TypeScript is an open-source language that is built on top of JavaScript to provide build-time type checks.

TypeScript mimics syntax like statically typed language like Java and it helps to avoid runtime errors for JavaScript and detect the problem at build time.

Types in typescript provide you documentation plus build-time validation. The language is syntactic sugar and only present at the built time as typescript compiler code generates corresponding javascript code. So the types of typescript are not present at run time.

#### Example:

if you access some property or method which is not defined, JavaScript may not complain but typescript can help to detect it even before typescript code is converted to Javascript code.


## What is a trailing comma and why does it matter in typescript?

Trailing commas (sometimes called "final commas") is useful when adding new elements, parameters, or properties in JavaScript types like objects, arrays, functions parameters, and arguments, etc.

JavaScript has allowed trailing commas in array literals since the beginning, and later added them to object literals ([ECMAScript 5](https://en.wikipedia.org/wiki/ECMAScript#5th_Edition)) and most recently ([ECMAScript 2017](https://en.wikipedia.org/wiki/ECMAScript#8th_Edition_%E2%80%93_ECMAScript_2017)) to function parameters.

As typescript is built on top of JavaScript it also allows trailing-commas as valid syntax.

#### Example:

- Use in enum

The last entry in enum has a command which is an example of a trailing comma.

```
enum CountryName {
  INDIA,
  USA,
  SINGAPORE,
  CANADA,
  }

```
  
 - Use in the array declaration 
 
 ```
  const nums:number[] = [
  1,
  2,
  3,
  ]
 
 ```
 
 - Use in object 
 
```
interface Person {
   name:string;
   age:number;
  }

const person: Person =  {
 "name": "Nilesh Salpe",
  "age" : 30,
} as Person;

```

- Use in functional parameters and arguments 

```
class Person {

  name(name:string, age:number,) :string {
      return "My " + name + "age is "+ age;

  }
}

```

## What are the advantages of using trailing commas?

- If you want to add a new property, you can add a new line without modifying the previously last line if that line already uses a trailing comma. 
This makes version-control diffs cleaner and editing code might be less troublesome.
It helps in code review and also in tracking change example in the case of using [git-blame](https://git-scm.com/docs/git-blame)

- It helps to resolve conflicts automatically in version control systems like git. 
From personal experience, I have seen conflict in such cases, in java code which I have to resolve manually. By the way, Java does not allow such commas.

### What are the disadvantages of using trailing commas?

- There are no apparent disadvantages of using trailing commas. 
    - If your construct introduces new line example enum, array entry, JSON object, etc. then we should use this rule.
    - If you construct do not introduce new line example one line array declaration, functional parameters, or arguments in such cases it is nice to have but not mandatory.

- Reason given that JavaScript source code size increases, is not applicable as it is very insignificant.
 
## References 
 - [mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas)
- [TypeScipt Language](https://www.typescriptlang.org/)
