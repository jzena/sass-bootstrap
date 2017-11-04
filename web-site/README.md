# FIRST PROJECT WITH SASS

## Dependencies
- [Sass](http://sass-lang.com/)
- [Sass guide](http://sass-lang.com/guide)
- [Ruby installer](https://rubyinstaller.org/)

## Commands
- `gem install sass`
- `cd web-site`
- `sass --watch sass:css`

### Nesting
```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

### Mixins
```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }

@mixin css3-prefix($property, $value) {
  -webkit-#{$property}: #{$value};
   -khtml-#{$property}: #{$value};
     -moz-#{$property}: #{$value};
      -ms-#{$property}: #{$value};
       -o-#{$property}: #{$value};
          #{$property}: #{$value};
}
@mixin border-radius($radius: 4px) {
	@include css3-prefix("border-radius", $radius);
}
```

### Extend/Inheritance
```scss
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}

.warning {
  @extend .message;
  border-color: yellow;
}
```
### Operators
```scss
.container { width: 100%; }


article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
```
