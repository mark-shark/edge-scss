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

    npm i @edge-code/edge-scss

And put the @import url in the project root style-file.scss

    @import "node_modules/@edge-code/edge-scss/edge-core";

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

#### @example in your project style-file.scss or root core.scss

    @import "node_modules/@edge-code/edge-scss/edge-core";  //On Top

    @include make-host;                  // :host @mixin
    @include make-html;                  // html  @mixin
    @include make-body();                // body  @mixin
    @include make-box-sizing;            // box-sizing  @mixin

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

    "xs"  : 0
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
- make-base($val);
- make-host();
- make-html();
- make-body($val);
- make-box-sizing();
- make-clearfix();
- make-list-unstyled();

###### breakpoints @mixin
- media-screen-min(1001px) { @content };
- media-screen-max(1000px) { @content };
- media-min($val) { @content };
- media-max($val) { @content };
- media-between($val, $val) { @content };

###### layout @mixin
- make-row();
- make-row-cols();
- make-col-ready();
- make-col-auto();
- make-col-offset();
- make-col-(1 until 12 or empty);
  - make-col-xs-(1 until 12);
  - make-col-sm-(1 until 12);
  - make-col-md-(1 until 12);
  - make-col-lg-(1 until 12);
  - make-col-xl-(1 until 12);
  - make-col-xxl-(1 until 12);
- make-cssgrid();
- make-grid-columns();
- make-grid-col();
- make-grid-ready($gap, $gap);
  - make-grid-wrap();
  - make-grid-main();
  - make-grid-aside($gap, $gap);
  - make-grid-header();
  - make-grid-footer();

###### images @mixin
- make-img-fluid();
- make-img-thumbnail();
- make-figure();
- make-figure-img();
- make-figure-caption();

###### buttons @mixin
- make-btn($radius, $bg-btn, $color, $padding, $width);

###### colors @mixin
- make-color-scheme($name);

###### We will develop more

---
#### The library will take care of the rest.
### Good luck in your work.
