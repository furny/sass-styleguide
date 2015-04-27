# Sass Styleguide

## Methodology

We use the BEM – Block, Element, Modifier paradigm for writing our Sass. The following section describes the naming and gives an usage example.

### Naming

  * **Blocks** should have a descriptive and unique name.
  * **Elements** are a part of a block and have no standalone meaning. The class is formed as block name plus two underscores plus element name: ``.block__element``.

  * **Modifier** are flags on blocks that changes their appearance or behavior. A modifier can either be a boolean flag or a key / value pair. In both cases the delimiter is a single underscore. Boolean flag: `.block_modifier` or `.block__element_modifier` - Key / value modifier: `.block_key_value` or `.block__element_key_value`.

### Usage example

An example for a `list` module which will be constructed of

  * the list container
  * a header
  * a body
  * and a footer

```css
$module: 'list';

.#{$module}__header {
    background: tomato;
    color: #fff;
}

.#{module}__body {
    font-size: 180%;    
}

.#{module}__footer {
    background: green;
    padding: 0 .2em;
}

.#{module}__footer-huuuuuge 
    font-size: 200%;
}

```
## Folder structure

```sh
sass/
|- base/
|  |-- colors.scss
|  |-- fonts.scss
|  |-- _index.scss
|- mixins/
|  |-- a-mixin.scss
|  |-- another-mixin.scss
|  |-- _index.scss
|- modules/
|  |-- button.scss
|  |-- product.scss
|  |-- list.scss
|  |-- _index.scss
|- app.scss
```

  * **base**: All common definitions like colors and fonts but no layout definitions(!).
  * **mixins**: Library of shared mixins which can be used by all modules.
  * **modules**: A module contains all necessary definitions for a logical unit of one block, with one or multiple elements and one or multiple modifiers.
  * The index files which encapsulates all the imports within the current directory gets a underscore as a prefix.
  * `app.scss` will import all `_index.scss` files from the subdirectories.


The directory structure above will be transformed into

```sh
styles/
|- app.css
```

## Whitespace

  * Use soft tabs set to 4 spaces.

  ```sass
  // bad
  .block {
  ∙∙color: tomato;
  }

  // good
  .block {
  ∙∙∙∙color: tomato;
  }
  ```

## Attributes

  * Should have a whitespace between the `:` and the actual value

  ```sass
  // bad
  .list {
      background:tomato;
  }

  // good
  .list {
      background: tomato;
  }
  ```