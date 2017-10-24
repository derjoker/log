# SCSS

### Sass vs. SCSS

Sass: Syntactically Awesome Style Sheets

SCSS: Sassy CSS

### _ (partials)

> The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file.

```
// _partial.scss
```

```
// base.scss
@import partial
```

注意: @import partial (而不是_partial)

### `$white: #fff !default;`

> You can assign to variables if they **aren’t already assigned** by adding the !default flag to the end of the value. This means that if the variable has already been assigned to, it **won’t be re-assigned**, but if it doesn’t have a value yet, it will be given one.

### mixin & include

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

```css
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

### mixin: object or function?

```scss
@mixin hover {} // 无参数
```

```scss
@mixin button-variant($background, ...) {} // 函数
```
