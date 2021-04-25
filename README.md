# Sass_Usages
Common usages of Sass pre-css-processor


### Preface
Webpack modules bundler only handle Javascript and JSON files, if you using Sass in your project, then have to add loaders In Webpack config-file...  

### @mixin Usages in Responsive web case:
1. define Mixins Variables in minxin.scss file , Then using Vue CLI - vue.config.js to include the Mixins.scss as Data Attribute.  
    ```javascript
    //minxins.scss
    @mixin respond($breakpoint) {
    @if $breakpoint == phone {
        @media only screen and (min-width: 20em) and (max-width: 48em) {
            @content;
        }
    }

    @if $breakpoint == tablet-portrait {
        @media only screen and (min-width: 48em) and (max-width: 64em) and (orientation: portrait) {
            @content;
        }
    }

    @if $breakpoint == tablet-landscape {
        @media only screen and (min-width: 48em) and (max-width: 64em) {
            @content;
        }
    }

    @if $breakpoint == desktop {
        @media only screen and (min-width: 64em) and (max-width: 114em) {
            @content;
            }
        }
    }
    ```
2. using vue.config.js file to set CSS and loaders
    ```javascript
    module.exports = {
    css: {
        loaderOptions: {
            sass: {
                data: `@import "@/assets/scss/abstract/mixins.scss";`
            }
        }
    },
   
    };

    ```
3. In your index.html page, you want to write Responsive css Code via SASS, then:
```css
    header {
    background: #18191c;
    border-bottom: 1px solid #fff;
    width: 100%;
    position: relative;
    z-index: 10;

    @include respond(phone) {
        position: fixed;
        top: 0;
        }
    }
```
