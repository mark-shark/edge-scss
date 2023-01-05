# EDGE-scss

---
### SCSS Dynamic @mixin library for developing responsive.
#### EDGE is simple SCSS @mixin library originating from [Bootstrap](https://getbootstrap.com/) (v5.0).
- Primarily created for Angular 7 and newer. 
- To achieve as little as possible in CSS compilation.

---
#### Assumptions 
Experiences with SCSS, SASS, NPM.

---
##### [Playground](https://stackblitz.com/edit/angular-ivy-cdlzyj?file=src/app/app.component.scss)

---
## Install

Use [NPM](https://www.npmjs.com/) and [@SASS](https://sass-lang.com/) 

1.  `npm install @edge-code/edge-scss`

And put the @import url in the project root style-file.scss
2.  `@import "node_modules/@edge-code/edge-scss/edge-core";`

---
## Usage and Documentation

How use [@mixin and @include](https://sass-lang.com/documentation/at-rules/mixin).

#### @example your index.html or template component.

    <!DOCTYPE html>
    <html>
      <head>
        < .../>
      </head>
      <body>
        < .../>

        <div class="my-container">
            <div class="my-row">
                <div class="my-col">
                  @Some Content
                  <a href="#" class="my-btn"></a>
                </div>

                <div class="my-col">
                  @Some Content
                </div>
            </div>
        </div>

        < .../>
      </body>
    </html>

#### In your project style-file.scss or root core.scss

@example.scss

    @import "node_modules/@edge-code/edge-scss/edge-core";  //On Top

    @include make-box-sizing;
    @include make-body(320px);

    .my-container {
        @include make-container;    // .container  @mixin

        //Your Declaration Content or Next @mixin
    }

    .my-row {
        @include make-row;          // .row  @mixin
        //Your Declaration Content or Next @mixin
    }
    
    .my-col {
        @include make-col(12);      // .col-12     @mixin
        @include make-col-md(6);    // .col-md-6   @mixin col 
        @include make-col-xl(3);    // .col-xl-3   @mixin col

        //Your Declaration Content or Next @mixin
    }

    .my-btn {
        @include make-btn(
            $radius: .25rem,    // radius
            $bg-btn: purple,    // background-color
            $color: white,      // color
            $padding: 2rem,     // padding
            $width: 100%,       // width
        );
        //Your Declaration Content or Next @mixin
    }

@example.css

    *, ::after, ::before {
      box-sizing: border-box;
    }
    body  {
      display: block;
      margin: 0;
      padding: 0;
      min-width: 320px;
    }
    .my-container {
      width: 100%;
      max-width: 100%;
      margin: 0 auto;
      padding: 0 16px;
    }
    .my-row {
      --edge-gutter-x: 1.5rem;
      --edge-gutter-y: 0;
      width: 100%;
      max-width: 100%;
      display: flex;
      flex-flow: row wrap;
      margin-top: calc(-1 * var(--edge-gutter-y));
      margin-right: calc(-0.5 * var(--edge-gutter-x));
      margin-left: calc(-0.5 * var(--edge-gutter-x));
    }
    .my-col {
      flex: 0 0 auto;
      width: 100%;
    }
    @media (min-width: 768px) {
      .my-col {
        flex: 0 0 auto;
        width: 50%;
      }
    }
    @media (min-width: 992px) {
      .my-col {
        flex: 0 0 auto;
        width: 25%;
      }
    }
    .my-btn {
      --edge-gutter-x: 0;
      --edge-gutter-y: 1.5rem;
      width: fit-content;
      width: -moz-fit-content;
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      cursor: pointer;
      height: calc(1.5 * var(--edge-gutter-y));
      border-radius: 0.25rem;
      color: white;
      background-color: purple;
      padding: 0 2rem;
      width: 100%;
    }
    .my-btn:active {
      color: white;
      text-decoration: none;
    }
    .my-btn:hover {
      background-color: #993399;
      color: white;
      text-decoration: none;
    }
    .my-btn:visited {
      color: white;
      text-decoration: none;
    }
    @media (min-width: 768px) {
      .my-btn {
        height: calc(1.667 * var(--edge-gutter-y));
      }
    }
    @media (min-width: 992px) {
      .my-btn {
        height: calc(2 * var(--edge-gutter-y));
      }
    }

---
### Breakpoints
| Breakpoints | Value  |
|-------------|--------|
| XS          | 321px  |
| SM          | 576px  |
| MD          | 768px  |
| LG          | 992px  |
| XL          | 1200px |
| XXL         | 1400px |

---
@example.scss Breakpoints

    .my-class {
      // Example Media Query Min
      @include media-min(md) { 
          //Your Declaration Content or Next @mixin
      }
      @include media-min(xxl) { 
          //Your Declaration Content or Next @mixin
      }
      //Or Max
      @include media-max(xl) { 
          //Your Declaration Content or Next @mixin
      }
    }

@example.css

    @media (min-width: 768px) {
      .my-class {
        //Your Declaration
      }
    }
    @media (min-width: 1400px) {
      .my-class {
        //Your Declaration
      }
    }

    @media (max-width: 1199.98px) {
      .my-class {
        //Your Declaration
      }
    }

---
### Breakpoints Individual
@example.scss

    .my-class {
      @include media-screen-min(951px) {  // @mixin Media Query Min
          //Your Declaration Content or Next @mixin
      }
      
      @include media-screen-max(950px) {  // @mixin Media Query Max
          //Your Declaration Content or Next @mixin
      }
    }

@example.css

    @media (min-width: 951px) {
      .my-class {
        //Your Declaration
      }
    }

    @media (max-width: 950px) {
      .my-class {
        //Your Declaration
      }
    }

---
### Breakpoints in GRID default
| Breakpoints | Columns    |
|-------------|------------|
| 0           | 1 column   |
| XS          | 2 columns  |
| SM          | 4 columns  |
| MD          | 6 columns  |
| LG          | 8 columns  |
| XL          | 10 columns |
| XXL         | 12 columns |

---
### List [@mixin and @include](https://sass-lang.com/documentation/at-rules/mixin) ...

        
| Name @mixin                                             | Description                                                                                                                                                          |
|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| base @mixin                                             |                                                                                                                                                                      |
| `make-host();`                                          | Creates and specify a basic declaration with a :host element.                                                                                                        |
| `make-html();`                                          | Creates and specify a basic declaration with a html element.                                                                                                         |
| `make-body($val);`                                      | Creates and specify a basic declaration with a body element. Add a value for the minimum width, but you don't have to.                                               |
| `make-box-sizing();`                                    | Creates and specify a declaration for all element.                                                                                                                   |
| `make-clearfix();`                                      | Creates and specify a declaration for all element.                                                                                                                   |
| `make-list-unstyled();`                                 | Creates and specify a basic declaration for list element.                                                                                                            |
| breakpoints @mixin                                      |                                                                                                                                                                      |
| `media-screen-min() { @content };`                      | Creates and specify a derivative declaration for @media query with own content declaration. Specify a own value.                                                     |
| `media-screen-max() { @content };`                      | Creates and specify a derivative declaration for @media query with own content declaration. Specify a own value.                                                     |
| `media-min() { @content };`                             | Creates and specify a derivative declaration for @media query with own content declaration. Specify a prescribed value.                                              |
| `media-max() { @content };`                             | Creates and specify a derivative declaration for @media query with own content declaration. Specify a prescribed value.                                              |
| `media-between() { @content };`                         | Creates and specify a derivative declaration for @media query with own content declaration. Specify a prescribed value.                                              |
| layout @mixin                                           |                                                                                                                                                                      |
| `make-container();`                                     | Creates and specify a complete declaration for container element or section. Add value sm, md, lg, xl, xxl and fluid.                                                |
| `make-row();`                                           | Creates and specify a complete declaration for row element. Flex element.                                                                                            |
| `make-row-cols();`                                      | Specify on a parent element(e.g., .row) to force immediate children into NN number of columns. Supports wrapping to new lines, but does not do a Masonry style grid. |
| `make-col-ready();`                                     | Creates and specify a basic declaration for column element.                                                                                                          |
| `make-col-();`                                          | Creates and specify a complete declaration for column element. Add a value for the width, but you don't have to. (1 - 12)                                            |
| `make-col-xs-();`                                       | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-sm-();`                                       | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-md-();`                                       | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-lg-();`                                       | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-xl-();`                                       | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-xxl-();`                                      | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |                                                                                                                                                                                                                                                                                                                                  |
| `make-grid-ready($gap, $gap);`                          | Creates and specify a basic declaration for grid wrap element.                                                                                                       |
| `make-grid-main();`                                     | Creates and specify a basic declaration for main element.                                                                                                            |
| `make-grid-aside($gap, $gap);`                          | Creates and specify a basic declaration for aside element.                                                                                                           |
| `make-grid-header();`                                   | Creates and specify a basic declaration for header element.                                                                                                          |
| `make-grid-footer();`                                   | Creates and specify a basic declaration for footer element.                                                                                                          |
| images @mixin                                           |                                                                                                                                                                      |
| `make-img-fluid();`                                     | Creates and specify a basic declaration for an auto-width image element.                                                                                             |
| `make-img-thumbnail();`                                 | Creates and specify a basic declaration for a thumbnail element.                                                                                                     |
| `make-figure();`                                        | Creates and specify a basic declaration for a figure element.                                                                                                        |
| buttons @mixin                                          |                                                                                                                                                                      |
| `make-btn-ready();`                                     | Creates and specify a basic declaration for button element.                                                                                                          |
| `make-btn($radius, $bg-btn, $color, $padding, $width);` | Creates and specify an advanced declaration for button element.                                                                                                      |
| colors @mixin                                           |                                                                                                                                                                      |
| `make-color-scheme($name);`                             | Creates and specify a declaration for color scheme.                                                                                                                  |

###### ** We will develop more.

---
#### The library will take care of the rest.
### Good luck in your work.
