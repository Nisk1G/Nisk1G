# Tex

## SetUp

[これ](https://qiita.com/rainbartown/items/d7718f12d71e688f3573#%E5%AE%9F%E9%9A%9B%E3%81%AB%E4%BD%BF%E3%81%A3%E3%81%A6%E3%81%BF%E3%82%88%E3%81%86)やればいい

## Use Tips

- commit前にはctrl+alt+Cで生成ファイル消してディレクトリ綺麗に！！
- 表と図を横に並べたい

\begin{document}の前に
```
\makeatletter
\newcommand{\figcaption}[1]{\def\@captype{figure}\caption{#1}}
\newcommand{\tblcaption}[1]{\def\@captype{table}\caption{#1}}
\makeatother
```
を書いて,
```
\begin{figure}[h]
  \def\@captype{table}
  \begin{minipage}[c]{.48\textwidth}
    \tblcaption{左側の表の見出し}
    \label{左側の表へのラベル}
    \centering
      \begin{tabular}{}

        左側の表

      \end{tabular}
  \end{minipage}
  %
  \hfill
  %
  \begin{minipage}[c]{.48\textwidth}

    右側に配置する図
      例: \resizebox{\textwidth}{!}{\input{hogehoge.tex}}

    \caption{図の見出し}
    \label{図へのラベル}
  \end{minipage}
\end{figure}
```
[参考元](http://www-an.acs.i.kyoto-u.ac.jp/~fujiwara/tex/nup.html)より一部改変