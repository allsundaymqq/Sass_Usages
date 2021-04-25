# Sass_Usages
Common usages of Sass pre-css-processor


### Preface
Webpack modules bundler only handle Javascript and JSON files, if you using Sass in your project, then have to add loaders In Webpack config-file...  

### Usages:
1. define Mixins Variables in Minxin.scss file , Using Vue CLI - vue.config.js to include the Mixins.scss as Data Attribute.  
    `  //minxins.scss
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
    `
