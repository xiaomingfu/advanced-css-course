### Sec2 Natours Project - setup and first steps

- using the universal selector `*` to do a basic reset
- set project-wide font defitions
- clip parts of elements with `clip-path`
- using `span` tag in `h1` tag to get block display two line of heading
- using `transform: translate(-50%, -50%)` to corect the position based on the elements width and height
- animation
- pseudo-elements and pseudo-classes
- `::after`
- using `transition` property to create a creatitve hover animation effect

### Sec3 How CSS words

- Responsive design

  - Fluid layouts
  - Media queries
  - Responsive images
  - Correct units
  - Desktop-first vs mobile-first

- Maintainable and scalable code

  - Clean
  - Easy-to-understand
  - Growth
  - Reusable
  - organize files
  - name classes
  - structure html

- Web performance
  - Less HTTP requests
  - Less code
  - Compress code
  - CSS preprocessor
  - Less image
  - Compress images

#### Webpage load up

![Webpage load up](./courseImgs/webpage-loadup.png)

- CSS terminology
  ![CSS RULE](./courseImgs/css-terminology.png)
- Cascade
  ![Cascade](./courseImgs/cascade.png)
- Cascade order
  ![cascade order](./courseImgs/cascade-order.png)

> Conclusion:
>
> - `!important`: have the highest priority, but only use it as a last resource, for it > maintainable problem.
> - Inline styles' priority over styles in external stylesheets
> - ID > class > element
> - universal selector `*` has no specificity value(0,0,0)
> - Rely more on specificity than on the order of selectors

#### CSS values process

- CSS values
  ![css value](./courseImgs/css-values-process.png)
- Units -> PX
  ![units to px](./courseImgs/units-px.png)

#### CSS Inheritance

![css inheritance](./courseImgs/css-inheritance.png)

- Inheritance make more maintainable code
- Properties related to text are inherited: `font-family`, `font-size`, `color`, etc
- The computed value of a property is what gets inherited, not the declared value
- `inherit` keyword forces inheritance
- `initialize` keyword resets to its initial value

```css
html {
  font-size: 62.5%; /* 10/16 */
}
body {
  padding: 2rem; /* 2*10px */
}
```

#### Visual Formatting Model

![Visual Formatting Model](./courseImgs/visual-formatting-model.png)

- Box Model
  ![box model](./courseImgs/box-model.png)

  - Box Model with `box-sizing: border-box`
    ![border box](./courseImgs/border-box.png)

- Box Type
  ![box types](./courseImgs/box-types.png)

- Positioning Schema
  ![positioning schemas](./courseImgs/positioning.png)

- Stacking Contexts
  ![stacking contexts](./courseImgs/stacking.png)

#### Thinking the Layout

- Think -> Build -> Achitect
  - Component-Driven Design
    ![think](./courseImgs/think.png)
  - BEM(Block Element Modifier)
    ![BEM](./courseImgs/BEM.png)
  - 7-1 Pattern
    ![7-1 pattern](./courseImgs/architect.png)

### Sec4 Intro to Sass

- Sass is a CSS preprocessor. an extension of CSS.
- features
  ![Sass features](./courseImgs/Sass-features.png)

  - Variables: `$color-primary: #fff`
  - Nesting:
    ```Sass
    .btn{
        &:link{
            color: $color-primary;
        }
    }
    ```
  - Mixin:

    ```Sass
    @mixin clearfix{
        &::after{
            content: '';
            clear: both;
            display: table;
        }
    }

    nav{
        @include clearfix;
    }
    ```

  - Function:

    ```Sass
    @function divide($a, $b){
        @return $a / $b
    }
    margin: divide(60, 2)
    ```

  - Extends:

    ```Sass
    &btn-placeholder{
        padding: 10px;
        display: inline-block;
    }

    .btn-main{
        &:link{
            @extend %btn-placeholder;
        }
    }
    ```
