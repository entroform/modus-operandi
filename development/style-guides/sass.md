# SASS Style Guide

- Use soft tabs (2 spaces) for indentation.
- Avoid using Ids.
- Always add a new line in-between rules.
- Use `camelCase` in between dashes.

## Use BEM

Use a mix of [BEM](https://en.bem.info/methodology/) and [OOCSS](http://thesassway.com/intermediate/using-object-oriented-css-with-sass).

Use BEM for writing specific style rules and to avoid deep nestings.
Use OOCSS for writing more general and global rules.

## Directory Structure

This would probably vary between projects.

I think it is a good idea to have a folder dedicated for `globals`.

```
- main.scss
- views
- app
- _reset.scss
- global
-- _index.scss
-- variables
--- _index.scss
--- _colors.scss
--- _fonts.scss
-- placeholder-classes.scss
-- mixins.scss
-- utilities.scss
```

## Naming Conventions

Use `camelCase` as primary and `-` dashes to add prefixes, suffixes, or different levels.

### Prefixes

Anything used for JavaScript references should have
`js-` prefixes and should not have any styling on it.

Anything that references JavaScript should be very specific.

```
js-[target]-[action]
js-page-menuButton-open
```

Other acceptable prefixes:

- `global-` Global.
- `page-` Page specific.
- `site-` Site wide.

## Naming Class Selectors

Dashes are used to denote different levels.
For example:

- `.page-home-hero`
- `.page-blog-blogPost`

It is important to be specific for root level classes and more general for nested level.

```scss
.page-home-hero {
  // Here is an example where BEM comes handy to avoid deep nesting.
  // Always try to keep it flat.
  .header {
    .header__title {
      //...
    }

    .header__subtitle {
      //...
    }
  }
}
```

### Declarations

- Keep declarations in alphabetical order.

- Use line break to separate variable declarations, placeholder classes, mixins, transition declarations, animation declarations, and base declarations.

- The order inside the block should be: block variables, extends, includes,
base declarations, transition declarations, and animation declarations.

```scss
.example {
  $__size: 50px;

  @extend %something;

  @include some-mixin($__size);

  display: block;
  position: fixed;
  top: 0;
  width: $__size;

  transition-duration: 200ms;
  transition-timing-function: ease-out;

  animation-duration: 200ms;
  animation-name: fade-in;
}
```

### Naming Variables

```scss
// Constants should use SCREAMING_SNAKE_CASE.
$GLOBAL_CONSTANT: 'something';

// Available globally throughout the entire project.
$global: 'something';

// Local to file: something.scss
$_local: 'blue';

.block {
  // Block level.
  $__block: 'something';
}
```

### Maps

Wrap map keys in single-quote and always add trailing commas
at the end for nested maps.

```scss
// Bad
$colors: (
  primary: (
    base: hsl(240, 100, 50),
    hover: hsl(240, 100, 75)
  )
);

// Good
$colors: (
  'primary': (
    'base': hsl(240, 100, 50),
    'hover': hsl(240, 100, 75),
  ),
);
```

### Functions, Mixins, and Controls

Functions and Mixins follow a similar rule as variables.
```scss
// Use local or block level variable naming convention for parameters.
@function global-function($_font-family) {
  // @return ...
}

@function _local-function($__something) {
  // @return ...
}

@mixin _local-mixin() {
  // ...
}
```

## Links

- [Airbnb's CSS/SASS Styleguide](https://github.com/airbnb/css)
- [MindBEMding](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
- [CSS Tricks: BEM101](https://css-tricks.com/bem-101/)
- [SuiteCSS](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md)
- [SASS Guidelines](https://sass-guidelin.es/#loops)

## Resources

- [Introduction to Error Handling in SASS](https://webdesign.tutsplus.com/tutorials/an-introduction-to-error-handling-in-sass--cms-19996)
