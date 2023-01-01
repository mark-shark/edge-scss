# EDGE-scss

Dynamic @mixin library
---

EDGE is simple @mixin library originating from Bootstrap (v5.0).

- Primarily created for Angular projects. 
- To achieve as little as possible in CSS compilation.

---

Install - put the @import url in the project root. 

    @import "../edge-core"; 

---

@example your-index.html

    <div class="my-container">
        <div class="my-row">
            <div class="my-col"></div>
            <div class="my-col"></div>
        </div>
    </div>

---

@example in project your-style.scss or root core.

    @import "../edge-core"; //On Top

    .my-container {
        @include make-container; //@mixin

        //Your Declaration Content
    }

    .my-row {
        @include make-row; //@mixin

        //Your Declaration Content
    }
    
    .my-col {
        @include make-col(12); //@mixin
        @include make-col-md(6); //@mixin col 
        @include make-col-xl(3); //@mixin col

        //Your Declaration Content

        // Example Media Query Min
        @include media-min(md) { //@mixin @media (min-width: 768px)
            //Your Declaration Content
        }
        //Or Max
        @include media-max(md) { //@mixin @media (max-width: 767px)
            //Your Declaration Content
        }

        //Or Individual
        @include media-screen-max(950px) { //@mixin Media Query Max
            //Your Declaration Content
        }
        @include media-screen-min(951px) { //@mixin Media Query Min
            //Your Declaration Content
        }
    }

---

Good luck in your work.

---

(v0.0.1)

- Start project.
- Compiled from Bootstrap (v5.0) variables, @mixin, @function.
- Own function for
    - media-query 
    - col
    - container
    - btn
    - grid - wrap, header, aside, main, footer
---
