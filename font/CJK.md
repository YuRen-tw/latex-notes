**LaTeX 筆記**｜[首頁](../README.md)｜[字型](font.md)

-------------

# 中文

> 先寫下來，之後再補內文


```tex
\usepackage{fontspec}
\newfontfamily{\CJK}{Noto Sans CJK TC}

{\CJK 漢字}
```


```tex
\usepackage{fontspec}
\usepackage{xeCJK}
\XeTeXlinebreaklocale "zh"
\XeTeXlinebreakskip = 0pt plus 1pt
\setCJKmainfont{Noto Sans CJK TC}
```

`\setCJKmainfont[BoldFont=Noto Serif CJK TC Bold]{Noto Serif CJK TC}`

-------------

**LaTeX 筆記**｜[首頁](../README.md)｜[字型](font.md)

