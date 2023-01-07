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

    @import "your-variables";

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
| 0           | 2 column   |
| XS          | 2 columns  |
| SM          | 4 columns  |
| MD          | 6 columns  |
| LG          | 8 columns  |
| XL          | 10 columns |
| XXL         | 12 columns |

---
