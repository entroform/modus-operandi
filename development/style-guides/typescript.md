# Typescript Style Guide

- Use soft tabs (2 spaces) for indentation.

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
interface Size {
  width: number;
  height: number;
}
```

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

## undefined vs null

Use `null` for when you explicitly mean "the value you are looking for does not exist, unreachable, or unavailable" and
use  `undefined` for when "the value you are looking for did not exist and was never defined".


## Functions & Methods

Always add trailing-comma, when parameters are multiline, unless you are using spread syntax.

```typescript
// bad
function something(
  a: number,
  b: number,
  c: number
);

// good
function something(
  a: number,
  b: number,
  c: number,
);

// good
function something(
  a: number,
  ...c: number[]
);
```

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