**LaTeX 筆記**｜[首頁](../README.md)｜[數學](math.md)

-------------

# 矩陣

> 先寫下來，之後再補內文

## matrix

```tex
\[
  \begin{matrix}
    1 & 0 \\
    0 & 1
  \end{matrix}
\]
```

`pmatrix`、`bmatrix`、`vmatrix`

## array

```tex
\[
  \begin{array}{c | c}
    1 & 0 \\
    \hline
    0 & 1
  \end{array}
\]
```

### 增廣矩陣

```tex
\[
  \left[\!
  \begin{array}{c c c | c c c}
    1 & 3 & 0 & 1 & 0 & 0 \\
    3 & 1 & 9 & 0 & 1 & 0 \\
    0 & 9 & 3 & 0 & 0 & 1
  \end{array}
  \!\right]
\]
```

-------------

**LaTeX 筆記**｜[首頁](../README.md)｜[數學](math.md)

