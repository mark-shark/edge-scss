# EDGE-scss

# Dynamic @mixin library
EDGE is simple @mixin library originating from Bootstrap (v5.0).

---

Install - put the @import url in the project root. 

    @import "../edge-core"; 

---

@example in your project style.scss or root core.

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

        @include media-min(xs) {
            //Your Declaration Content
        }

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
