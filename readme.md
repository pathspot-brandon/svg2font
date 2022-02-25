# svg2font

svg2font is a command line tool based on font-carrier, designed to generate a variety of font files supported by current browsers from an svg.

## Install

### command line

```sh
npm install -g https://github.com/george-quzhi/svg2font.git
```

### node

```sh
npm install --save https://github.com/george-quzhi/svg2font.git
```

## Usage

### command line

```sh
svg2font ./test/svgs ./test/font/
```

```markdown
Positional arguments:
svgPath Input svg path
fontPath Output font path

Optional arguments:
-h, --help Show this help message and exit.
-v, --version Show program's version number and exit.
-u UNICODENUM, --unicodeNum UNICODENUM unicodeNum, Specifies the unicode start value of the font. default 60000。
(default plus 1)&#xEA61;。
-n FILENAME, --fileName FILENAME fileName, Specifies the name of the generated font file。default iconfont。
-f FONTFAMILY, --fontFamily FONTFAMILY fontFamily, font of the specified font-family。default iconfont。

                                              .iconfont {
                                                font-family: "iconfont" !important;
                                                font-size: 16px;
                                                font-style: normal;
                                                -webkit-font-smoothing: antialiased;
                                                -moz-osx-font-smoothing: grayscale;
                                              }

-c FONTCLASS, --fontClass FONTCLASS fontClass, Specifies the icon class prefix. default icon-。

                                              .icon-test-1:before {
                                                content: "\ea61";
                                              }

-r REVERSE, --reverse REVERSE font to svg Reverse, generate svg image from font file
svg2font ./test/font/iconfont.ttf ./test/svgs/svg -r true
```

### node

```js
var svg2font = require("svg2font");
svg2font.generate(svgPath, fontPath, {
  unicodeNum: 60000, //Specifies the unicode start value of the font.
  fileName: "iconfont", //Specifies the name of the generated font file.
  fontFamily: "iconfont", //Specifies the font-family of the font.
  fontClass: "icon-" //Specifies the icon class prefix.
});
```

# [Licence](LICENSE)

MIT
