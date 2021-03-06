## Font formats to use with `@font-face`
- **WOFF** - Web Open Font Format - supported in IE9+ and all modern browsers
- **WOFF 2** - second version of above, provides better compression, not supported in IE, partially supported in Safari
- **EOF** - Embedded OpenType - Microsoft's format supported in IE, not supported in Edge
- **TTF** - True Type Font - slightly better support than WOFF (supports also 2.* and 4.0-4.3 Android browsers), doesn't have piracy protection like WOFF
- **SVG** - format supported only in iOS and desktop Safari

If you don't have to support old Android devices and IE less than 9, you're ok to use **WOFF** format only.

## Font loading
Fonts are lazy-loaded after CSSOM is constructed and required files faces are determined. This behaviour may lead to flash of unstyled text - some browsers wait till a font file becomes available, rendering empty space by default, other render a fallback font and then swap it.

[webfontloader](https://github.com/typekit/webfontloader) can help with better management of font assets - eg. forcing fonts to load synchronously before rendering.
