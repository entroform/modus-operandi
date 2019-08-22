# Files and Folders Style Guide

Use `kebab-case` for file and folder names.
Additionally, use `_` underscore to add levels, prefixes, or suffixes.

Acceptable:

```
menu/icon_submit-product.svg
menu/icon_submit-product_hover.svg
```

Ideal:

```
icons/submit-product.svg
icons/hover/submit-product.svg
```

Always nest folders to avoid namespacing and to keep file names short.

There are occasions when using underscore for nesting is optimal. For example: When the directory
already have multiple nested folders.
Or you want the file name might be conflicting or too close with existing directories.
