**LaTeX 筆記**｜[首頁](README.md)

-------------

# 文件結構
LaTeX 檔案以純文字儲存（副檔名為 `.tex`），其中以特定語法來描述生成檔案的結構、內文、樣式。

這個部分會寫到 LaTeX 檔案裡面的結構。

## 整體結構
LaTeX 檔案的基本結構如下
```tex
\documentclass{...}
  ...
\begin{document}
  ...
\end{document}
```

在 `\documentclass{...}` 與 `\begin{document}` 之間的部分有人稱它為序言（preamble），這裡通常會放入一些會影響到整份輸出文檔的指令。而在 `\begin{document}` 與 `\end{document}` 之間的則是放入文檔輸出時會呈現的內文。

## 序言
### 文檔類型
LaTeX 的第一行用來宣告輸出文檔的類型，完整格式如下。
```tex
\documentclass[options]{class}
```
其中的 `class` 宣告文檔的類型，一般的文件通常只要用 `article` 就好。而對於特殊的需求，有內建的 `book` 用來輸出書籍、第三方套件提供的像是 `beamer` 用來輸出投影片。事實上關於文檔類型的內部設定都有特定的「類型檔」（副檔名為 `.cls`）做定義，我們也可以直接下載特定的類型檔來使用。

可選的 `options` 可以放入其他設定選項，比如內文字大小、輸出文檔的版面尺寸。（這方面我們可以使用其他第三方套件來做更詳細的設定）例如，一份 A4 大小、內文 12pt 的文件可以用下面的宣告。
```tex
\documentclass[12pt,a4paper]{article}
```

### 套件 Packages
LaTeX 內建的指令往往不夠應付我們的排版需求，而自己用內建的底層語法來編寫常常也相當複雜。這時我們通常就會選用第三方提供的套件，它們的設計往往比我們自己手刻還要方便與專業。

引用一個套件相當簡單，只要一行指令就能獲得套件提供的各種指令、字體等等。
```tex
\usepackage[options]{package}
```
其中的 `package` 是套件的名稱，`options` 是可選的其他設定。

## 內文
LaTeX 輸出的內文會放在 `\begin{document}` 與 `\end{document}` 之間。

### 開頭
一份文件的開頭可能有文件的標題、作者的資訊、文件發表的時間等等。LaTeX 對文件的開頭並沒有固定的組成格式，但還是有一些常用的指令可以使用，常見的開頭格式如下：
```tex
\begin{document}
  \title{LaTeX notes}
  \author{Yu-Ren Pan}
  \date{September 2019}
  \maketitle
  ...
\end{document}
```

其中 `\title` 宣告文件標題、`\author` 宣告文件作者、`\date` 宣告文件發表日期。如果沒有宣告 `\date`，LaTeX 通常會抓輸出文檔的日期。最後的 `\maketitle` 指令用來表示開頭已經宣告完成，接著排版引擎就會依照文檔類型安排這些開頭元素的位置；但如果沒有 `\maketitle`，這些開頭元素將不會被排版出來。

### 摘要
許多研究論文都會要求加入摘要，而在 LaTeX 中我們能在內文裡使用 `abstract` 環境來向排版引擎宣告文件的摘要內容。摘要通常會放在開頭之後，主要內文以前。
```tex
\begin{abstract}
  ... abstract ...
\end{abstract}
```

摘要的標題一般是「Abstract」，如果要改成其他文字，可以用 `\renewcommand` 重定義 `\abstractname` 這個指令。

### 章節
除了用空行來分段落以外，我們可以利用指令來分出層級更高的章節分隔。一般使用 `\section` 來分隔章節，對於層級更小的，有 `\subsection`、`\subsubsection` 等等。章節指令都需要一個參數作為章節標題。如果一份文件有目錄，那麼會以這些章節指令來組織目錄。章節會自動在標題前面添加編號。例如：
```tex
\section{First}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vulputate, velit vitae hendrerit scelerisque, nulla velit efficitur odio, eu ultricies sem lectus vel erat. Pellentesque in blandit ex.

Nullam tincidunt dapibus eros et fringilla. Praesent at nisl lorem. Fusce nec tristique odio. Donec a aliquam ex. Cras in ornare nunc. Donec volutpat libero sit amet tempor efficitur. Integer in mi non libero mollis porta.

\section{Second}

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vulputate, velit vitae hendrerit scelerisque, nulla velit efficitur odio, eu ultricies sem lectus vel erat. Pellentesque in blandit ex.
```
會被輸出成
![](../img/docstruct_sections.png)

-------------

**LaTeX 筆記**｜[首頁](README.md)

