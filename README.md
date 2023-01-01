# EDGE-scss
## Dynamic @mixin library
#### EDGE is simple SCSS @mixin library originating from Bootstrap (v5.0).
- Primarily created for Angular 7 and newer. 
- To achieve as little as possible in CSS compilation.
---
## Install

    npm i @edge-code/edge-scss

And put the @import url in the project root style-file.scss

    @import "node_modules/@edge-code/edge-scss/edge-core";

---
## Documentation
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

#### @example in your project style-file.scss or root core.scss

    @import "node_modules/@edge-code/edge-scss/edge-core";  //On Top

    @include host;                  // :host @mixin
    @include html;                  // html  @mixin
    @include body;                  // body  @mixin
    @include box-sizing;            // box-sizing  @mixin

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

        // Example Media Query Min
        @include media-min(md) {    // @mixin @media (min-width: 768px)
            //Your Declaration Content or Next @mixin
        }
        //Or Max
        @include media-max(md) {    // @mixin @media (max-width: 767px)
            //Your Declaration Content or Next @mixin
        }

        //Or INDIVIDUAL
        @include media-screen-max(950px) {  // @mixin Media Query Max
            //Your Declaration Content or Next @mixin
        }
        @include media-screen-min(951px) {  // @mixin Media Query Min
            //Your Declaration Content or Next @mixin
        }
    }

    .my-btn {
        @include make-btn(
            $radius: .25rem,    // radius
            $bg-btn: purple,    // background-color
            $color: white,      // color
            $padding-x: 2rem,   // padding
        );
        //Your Declaration Content or Next @mixin
    }

---
### Breakpoints

    "xs"  : 321px
    "sm"  : 576px
    "md"  : 768px
    "lg"  : 992px
    "xl"  : 1200px
    "xxl" : 1400px

    .my-class {
        // Example Media Query Min
        @include media-min(md) { 
            //Your Declaration Content or Next @mixin
        }
        //Or Max
        @include media-max(md) { 
            //Your Declaration Content or Next @mixin
        }
    }

---
### Breakpoints Individual

    .my-class {
        @include media-screen-max(950px) {  // @mixin Media Query Max
            //Your Declaration Content or Next @mixin
        }
        @include media-screen-min(951px) {  // @mixin Media Query Min
            //Your Declaration Content or Next @mixin
        }
    }

---
### Breakpoints GRID default

    "0"   : 1 column
    "xs"  : 2 columns
    "sm"  : 4 columns
    "md"  : 6 columns
    "lg"  : 8 columns
    "xl"  : 10 columns
    "xxl" : 12 columns

---
### List @mixin => @include ...
###### base @mixin
- base();
- host();
- html();
- box-sizing();
- clearfix();
- list-unstyled();

###### breakpoints @mixin
- media-screen-min();
- media-screen-max();
- media-min();
- media-max();

###### layout @mixin
- make-row();
- make-col-(1 until 12 or empty);
  - make-col-xs-(1 until 12);
  - make-col-sm-(1 until 12);
  - make-col-md-(1 until 12);
  - make-col-lg-(1 until 12);
  - make-col-xl-(1 until 12);
  - make-col-xxl-(1 until 12);
- make-col-grid();
- make-grid-ready($gap, $gap);
  - make-grid-wrap();
  - make-grid-main();
  - make-grid-aside($gap, $gap);
  - make-grid-header();
  - make-grid-footer();

###### images @mixin
- img-fluid();
- img-thumbnail();
- figure();
- figure-img();
- figure-caption();

###### buttons @mixin
- make-btn($radius, $bg-btn, $color, $padding-x);
- 

###### We will develop more

---
#### The library will take care of the rest.
### Good luck in your work.

---
### (v0.0.4)-alpha

- Start project.
- Compiled from Bootstrap (v5.0) variables, @mixin, @function.
- Own @mixin for:
    - media-query 
    - col
    - container
    - btn
    - grid - wrap, header, aside, main, footer
    - and more
---
