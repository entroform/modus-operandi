# Typescript Style Guide

## Table of Contents

- [Typescript Style Guide](#typescript-style-guide)
  - [Table of Contents](#table-of-contents)
  - [General](#general)
  - [Naming Conventions](#naming-conventions)
  - [Import](#import)
  - [Interfaces](#interfaces)
  - [Trailing Comma](#trailing-comma)
  - [Variables](#variables)
  - [Spacing](#spacing)
  - [Control Statements](#control-statements)
  - [Destructuring](#destructuring)
  - [Undefined vs Null](#undefined-vs-null)
  - [Overloads](#overloads)
  - [Classes](#classes)
    - [Order](#order)
  - [Links](#links)

## General

- Use soft tabs (**2 spaces**) for indentation.
- Always use single quotes instead of double quotes.
- Use semicolons.

## Naming Conventions

- **File and folder names** should be `kebab-cased`, see [Files and Folders Style Guide](./files-and-folders.md).
- **Classes and Interfaces** should be `PascalCased`.
- **Global constants and variables** should be `SCREAMING_SNAKE_CASED` (All uppercased).
- Other **variables and properties** should be `camelCased`.

## Import

Always break modules into multiple lines when importing, even when it's just one module and always add a trailing comma at the end.

The modules you are importing should also be sorted in alphabetical order.

```typescript
// Bad
import { Num, Util } from '@nekobird/rocket';

// Good
import {
  Num,
} from '@nekobird/rocket';

// Good
import {
  DOMUtil,
  Num,
  Util,
} from '@nekobird/rocket';
```

## Interfaces

Do not use "I" as prefix for interface names.

```typescript
// Bad
interface ISize {
  width: number;
  height: number;
}

// Good
interface Size {
  width: number;
  height: number;
}

// Okay?
interface IPhone {
  //...
}
```

## Trailing Comma

Use traling commas for `objects`, `literal types`, `functions`, when they are multi-line.

**Example**
```typescript
// Bad
const pokemons = [
  'jynx',
  'garbodor',
  'weezing'
];

// Good
const pokemons = [
  'pikachu',
  'eeve',
  'mew',
];

const pokemon = {
  name: 'pikachu',
  type: 'electric',
  color: 'yellow',
};

function doSomething(
  what,
  when,
  where,
) {
 // do something...
}

// rest element cannot have trailing comma
function doSomething(
  when,
  ...things[]
) {
  // do things...
}
```

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas

## Variables

- Avoid using single line variable declarations.
- Use whole words in names when possible.

```typescript
// Bad
let a, b;

// Good
let a;
let b;
```

## Spacing

Always break line in between unless after the beginning and at before the end of curly braces.

A few exceptions would be things that are very similar or closely related to each other.

```typescript
// Bad
doSomething();
doSomethingElse();
if (isSomething === true) {
  doAnotherThing();
  let something = getSomething();
}

// Good
doSomething();

doSomethingElse();

if (isSomething === true) {
  doAnotherThing();

  let something = getSomething();
}

// Acceptable
let isSomething = 'a';
let anotherSimilarThing = 'b';
```

## Control Statements

Keep operators at the beginning of line.

```typescript
// Bad
if (
  something() === true &&
  somethingElse() === true &&
  somethingSomethingElse() === true
) {
  doSomething();
}

// Good
if (
  something() === true
  && somethingElse() === true
  && somethingSomethingElse() === true
) {
  doSomething();
}
```

## Destructuring

Use destructuring when you can.

```typescript
// Array destructuring.
const names = ['Fluffy', 'Mona'];

// Bad
const dogName = names[0];
const catName = names[1];

// Good
const [dogName, catName] = names;
```

```typescript
// Object destructuring.
const point = {
  x: 0,
  y: 1,
};

// Bad
const x = point.x;
const y = point.y;

// Good
const { x, y } = point;
```

## Undefined vs Null

Use `null` for when you explicitly mean "the value you are looking for does not exist, unreachable, or unavailable" and
use  `undefined` for when "the value you are looking for did not exist and was never defined".

## Overloads

The order should be from **most** specific to **least** specific.
Additionally, use line-break in between overloads if the parameters are multi-line.

```typescript
function something(c: Cat): boolean;
function something(a: Animal): number;
function something(a: any): any {
  // Do something.
}

function somethingElse(
  a: number,
  b: number,
): number;

function somethingElse(
  a: number,
  b: any,
): boolean;
```

## Classes

### Order

`properties`, `constructor`, `methods`
`public`, `protected`, `private`, `static`

## Links

- [Microsoft TypeScript Coding Guidelines](https://github.com/Microsoft/TypeScript/wiki/Coding-guidelines)
- [Microsoft DotNet Design Guidelines](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines)
- https://dmitripavlutin.com/coding-like-shakespeare-practical-function-naming-conventions/
- https://medium.com/coding-skills/clean-code-101-meaningful-names-and-functions-bf450456d90c
- https://basarat.gitbooks.io/typescript/docs/styleguide/styleguide.html#enum