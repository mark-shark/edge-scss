<p style="text-align: center">
  <a href="https://github.com/mark-shark/edge-scss#readme">
    <img src="https://lh3.googleusercontent.com/aGuU3IVyGPI16_dc9fMKYD1KjnVVqmwc7p7PJ7uojdAP6C22BgtXrL3PCKHOfYqz_TOOZbAkqe5aaTorjzFzAqttivtbg_eNjsnJwSlRZEFIq7DgmU-IsaJSTCDkgWBM7StimwZZ1VfuDKKZGHBsEvQ5eHGZE-EwxxZ_bqiyEA1sbkJaFEJ03R210_tSR59xFCqlfT2wu1mPQLpHcUuwOJC3ehwko9kZbtJnk9r8spEv5qjFyIcjhhXV3_5MlPFLo6K8y0A1A0Xe1Ku4BvobYru1neprc3olgeEGKIdEJRdLCTjYnJwc2kRviLPmh2aJjsE_72K77x9AOmjjR5P8klrG4hXXCC-CtDJy7-SY-CAAPDsJHi4dbP7P9xWVcdQpGASpc3Uo6Fu24Wgm-OWv-J8mV6emz7PVqrhJKTETtNudx-qBmIDgKRugRk2FAudCuFbtNsasSodD1ZpQOJVmwdLJ2-GE-tCUnXjdwceM9gJLzygnYEcOeBPt1zAOaFB5yfoY2hQ2BV6PtWSIYdmJ9vp-t65MUuOZAfvhMT54tKLI9sELVmeykIqfLiGUDOPW0yaaluc5KSe0OwyKQttPTasp7xsNTVr7gWJLiiDAYuirwJk1iF1FWL4QgIWmglFqrdtWuqBxzh3VYnry6WXfEll_QmlXlPti4RQsDoISHHsAnx7olt9U7tKqzdP-pRXPmFonk2mICgsnKiHB29yCCS87UsAcqy_ENkNxqdslmeGXrkC7hiJcxkxcNwswFAbei0mOPsB0Tnge63bfI6SsLMK6qZy6-zYwYK6pnEu9reivBZZJNwIzBHlKQaygfjzs8Q7-y3RFv5YEkH4yRIyUse4RU3iLa4onu4Wn_B9l7ZbvEZ8wR2uKyhrq3xaWr7xcUfM_J2FL9VFBxcJ8up__gk_Uplg09r76Sl_QIu1Hc_Gs=s200-no?authuser=0" alt="Edge logo" width="200" height="200" title="Edge">
  </a>
</p>

<h3 align="center">EDGE-scss</h3>

---
### SCSS Dynamic @mixin library for developing responsive.
#### EDGE is simple SCSS @mixin library originating from [Bootstrap](https://getbootstrap.com/) (v5.0).
- Primarily created for Angular 7 and newer. 
- To achieve as little as possible in CSS compilation.

---
#### Assumptions 
Experiences with SCSS, SASS, NPM.

@Mixins are modified and treated to be reusable. For some you can add custom values.

---
##### [Playground](https://stackblitz.com/edit/angular-ivy-cdlzyj?file=src/app/app.component.scss)

---
## Install

Use [NPM](https://www.npmjs.com/) and [@SASS](https://sass-lang.com/) 

    npm i edge-scss@0.1.5-alpha3

And put the @import url in the project root style-file.scss

    @import "node_modules/edge-scss/edge-core";

---
### [Usage and Documentation](https://github.com/mark-shark/edge-scss/blob/main/Documentation.md)

---

### List [@mixin and @include](https://sass-lang.com/documentation/at-rules/mixin) ...

        
| Name @mixin                                                                     | Description                                                                                                                                                          |
|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| base @mixin                                                                     |                                                                                                                                                                      |
| `make-preflights();`                                                            | Creates and specify a declaration a basic element.                                                                                                                   |
| `make-host();`                                                                  | Creates and specify a basic declaration with a :host element.                                                                                                        |
| `make-html();`                                                                  | Creates and specify a basic declaration with a html element.                                                                                                         |
| `make-body();`                                                                  | Creates and specify a basic declaration with a body element. Add a value for the minimum width, but you don't have to.                                               |
| `make-box-sizing();`                                                            | Creates and specify a declaration for all element.                                                                                                                   |
| `make-clearfix();`                                                              | Creates and specify a declaration for all element.                                                                                                                   |
| `make-list-unstyled();`                                                         | Creates and specify a basic declaration for list element.                                                                                                            |
| breakpoints @mixin                                                              |                                                                                                                                                                      |
| `media-screen-min() { @content };`                                              | Creates and specify a derivative declaration for @media query with own content declaration. Specify a own value.                                                     |
| `media-screen-max() { @content };`                                              | Creates and specify a derivative declaration for @media query with own content declaration. Specify a own value.                                                     |
| `media-min() { @content };`                                                     | Creates and specify a derivative declaration for @media query with own content declaration. Specify a prescribed value.                                              |
| `media-max() { @content };`                                                     | Creates and specify a derivative declaration for @media query with own content declaration. Specify a prescribed value.                                              |
| `media-between() { @content };`                                                 | Creates and specify a derivative declaration for @media query with own content declaration. Specify a prescribed value.                                              |
| layout @mixin                                                                   |                                                                                                                                                                      |
| `make-container();`                                                             | Creates and specify a complete declaration for container element or section. Add value sm, md, lg, xl, xxl and fluid.                                                |
| `make-row();`                                                                   | Creates and specify a complete declaration for row element. Flex element.                                                                                            |
| `make-row-cols();`                                                              | Specify on a parent element(e.g., .row) to force immediate children into NN number of columns. Supports wrapping to new lines, but does not do a Masonry style grid. |
| `make-col-ready();`                                                             | Creates and specify a basic declaration for column element.                                                                                                          |
| `make-col-();`                                                                  | Creates and specify a complete declaration for column element. Add a value for the width, but you don't have to. (1 - 12)                                            |
| `make-col-xs-();`                                                               | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-sm-();`                                                               | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-md-();`                                                               | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-lg-();`                                                               | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-xl-();`                                                               | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |
| `make-col-xxl-();`                                                              | Creates and specify a full declaration for an auto-width column element. Add a value for the width. (1-12)                                                           |                                                                                                                                                                                                                                                                                                                                  |
| `make-grid-ready($gap-col, $gap-row);`                                          | Creates and specify a basic declaration for grid wrap element.                                                                                                       |
| `make-grid-main();`                                                             | Creates and specify a basic declaration for main element.                                                                                                            |
| `make-grid-aside($gap-col, $gap-row);`                                          | Creates and specify a basic declaration for aside element.                                                                                                           |
| `make-grid-header();`                                                           | Creates and specify a basic declaration for header element.                                                                                                          |
| `make-grid-footer();`                                                           | Creates and specify a basic declaration for footer element.                                                                                                          |
| modal @mixin                                                                    |                                                                                                                                                                      |
| `make-overlay();`                                                               | Creates and specify a basic declaration for modal overlay.                                                                                                           |
| `make-modal();`                                                                 | Creates and specify a basic declaration for modal container.                                                                                                         |
| colors @mixin                                                                   |                                                                                                                                                                      |
| `make-color-scheme($name);`                                                     | Creates and specify a declaration for color scheme.                                                                                                                  |
| UI                                                                              |                                                                                                                                                                      |
| images @mixin                                                                   |                                                                                                                                                                      |
| `make-img-fluid();`                                                             | Creates and specify a basic declaration for an auto-width image element.                                                                                             |
| `make-img-thumbnail();`                                                         | Creates and specify a basic declaration for a thumbnail element.                                                                                                     |
| `make-img-aspect();`                                                            | Creates and specify a declaration for a aspect-ratio.                                                                                                                |
| `make-figure();`                                                                | Creates and specify a basic declaration for a figure element.                                                                                                        |
| buttons @mixin                                                                  |                                                                                                                                                                      |
| `make-btn-ready();`                                                             | Creates and specify a basic declaration for button element.                                                                                                          |
| `make-btn($width, $height, $padding, $radius, $border, $background, $color, );` | Creates and specify an advanced declaration for button element.                                                                                                      |
| `make-btn-close($width, $color);`                                               | Creates and specify an advanced declaration for close button element.                                                                                                |


###### ** We will develop more.

---
#### The library will take care of the rest.
### Good luck in your work.
