参考：

- [https://www.latexlive.com/help](https://www.latexlive.com/help)
- [https://www.cnblogs.com/1024th/p/11623258.html](https://www.cnblogs.com/1024th/p/11623258.html) 

LaTeX 的发音为“Lah-tech”或“Lay-tech”（与“blech”或“Bertolt Brecht”押韵），是一种用于高质量排版的文档准备系统。
LaTeX, which is pronounced «Lah-tech» or «Lay-tech» (to rhyme with «blech» or «Bertolt Brecht»), is a document preparation system for high-quality typesetting.
虽然它最常用于大中型技术或科学文档，但是它几乎可用于任何形式的出版。
It is most often used for medium-to-large technical or scientific documents but it can be used for almost any form of publishing.

**MathJax**是一个跨浏览器的JavaScript库，它使用MathML、LaTeX和ASCIIMathML标记在Web浏览器中显示数学符号。


## 语法

两个 `$`符号包括就是latex公式，例如:$a+b=b+a$

## 字体

### 斜体

默认latex中的字母是**数学斜体**。例如：$a$

### 正体

 使用 \\mathrm{...} 可以将括号内的字母由数学斜体变为正体，即**罗马体**（roman type）。例如：$\mathrm{a}$

## 间距

| 预览            | 公式     | 说明     |
| ------------- | ------ | ------ |
| $I\,I$        | \\,    | 细小间距   |
| $I\:I$        | \\:    | 中等间距   |
| $I\;I$        | \\;    | 较大间距   |
| $I\quad I$    | \quad  | 标准间距   |
| "$I\qquad I$" | \qquad | 两个标准间距 |

## 特殊符号

| 预览           | 公式       | 说明                       |
| -------------- | ---------- | -------------------------- |
| $\#$         | \\#        | 在其前面加入 `\` 反斜杠 |
| $\%$         | $\%$     |                            |
| $\wedge$     | \wedge     |                            |
| $^\wedge$    | ^\wedge    |                            |
| $\&$         | \\&        |                            |
| $\_$         | \\_        |                            |
| $\{$         | \\{        |                            |
| $\}$         | \\}        |                            |
| $\sim$       | \sim       |                            |
| $\backslash$ | \backslash |                            |
## 字母
### 希腊字母（Greek letters）

| 序号  | 小写  | LaTeX       | 读音                     | 序号  | 大写  | LaTeX    | 读音          |
| --- | --- | ----------- | ---------------------- | --- | --- | -------- | ----------- |
| 1   | 𝛼  | \alpha      | /ˈælfə/                | 31  | Γ   | \Gamma   | /ˈɡæmə/     |
| 2   | 𝛽  | \beta       | /ˈbiːtə/, US: /ˈbeɪtə/ | 32  | Δ   | \Delta   | /ˈdɛltə/    |
| 3   | 𝛾  | \gamma      | /ˈɡæmə/                | 33  | Θ   | \Theta   | /ˈθiːtə/    |
| 4   | 𝛿  | \delta      | /ˈdɛltə/               | 34  | Λ   | \Lambda  | /ˈlæmdə/    |
| 5   | 𝜖  | \epsilon    | /ˈɛpsɪlɒn/             | 35  | Ξ   | \Xi      | /zaɪ, ksaɪ/ |
| 6   | 𝜀  | \varepsilon | /ˈɛpsɪlɒn/             | 36  | Π   | \Pi      | /paɪ/       |
| 7   | 𝜁  | \zeta       | /ˈzeɪtə/               | 37  | Σ   | \Sigma   | /ˈsɪɡmə/    |
| 8   | 𝜂  | \eta        | /ˈeɪtə/                | 38  | Υ   | \Upsilon | /ˈʌpsɪlɒn/  |
| 9   | 𝜃  | \theta      | /ˈθiːtə/               | 39  | Φ   | \Phi     | /faɪ/       |
| 10  | 𝜗  | \vartheta   | /ˈθiːtə/               | 40  | Ψ   | \Psi     | /psaɪ/      |
| 11  | 𝜄  | \iota       | /aɪˈoʊtə/              | 41  | Ω   | \Omega   | /oʊˈmeɪɡə/  |
| 12  | 𝜅  | \kappa      | /ˈkæpə/                |     |     |          |             |
| 13  | 𝜆  | \lambda     | /ˈlæmdə/               |     |     |          |             |
| 14  | 𝜇  | \mu         | /mjuː/                 |     |     |          |             |
| 15  | 𝜈  | \nu         | /njuː/                 |     |     |          |             |
| 16  | 𝜉  | \xi         | /zaɪ, ksaɪ/            |     |     |          |             |
| 17  | 𝑜  | o           | /ˈɒmɪkrɒn/             |     |     |          |             |
| 18  | 𝜋  | \pi         | /paɪ/                  |     |     |          |             |
| 19  | 𝜛  | \varpi      | /paɪ/                  |     |     |          |             |
| 20  | 𝜌  | \rho        | /roʊ/                  |     |     |          |             |
| 21  | 𝜚  | \varrho     | /roʊ/                  |     |     |          |             |
| 22  | 𝜎  | \sigma      | /ˈsɪɡmə/               |     |     |          |             |
| 23  | 𝜍  | \varsigma   | /ˈsɪɡmə/               |     |     |          |             |
| 24  | 𝜏  | \tau        | /taʊ, tɔː/             |     |     |          |             |
| 25  | 𝜐  | \upsilon    | /ˈʌpsɪlɒn/             |     |     |          |             |
| 26  | 𝜙  | \phi        | /faɪ/                  |     |     |          |             |
| 27  | 𝜑  | \varphi     | /faɪ/                  |     |     |          |             |
| 28  | 𝜒  | \chi        | /kaɪ/                  |     |     |          |             |
| 29  | 𝜓  | \psi        | /psaɪ/                 |     |     |          |             |
| 30  | 𝜔  | \omega      | /oʊˈmeɪɡə/             |     |     |          |             |

**注意:** MathJax支持的大写希腊字母有限，如需其他（如大写Alpha），可使用**罗马体**转换，如 `\mathrm{A}`表示大写Alpha：A。

### 希伯来字母 Hebrew alphabet

|序号|图标|LaTeX|英文|
|---|---|---|---|
|1|ℵ|\aleph|aleph|
|2|ℶ|\beth|beth|
|3|ℷ|\gimel|gimel|
|4|ℸ|\daleth|daleth|

## 运算符

### 四则运算符

| 预览       | 公式   | 说明 |
| ---------- | ------ | ---- |
| $+$      | +      | -    |
| $-$      | -      |      |
| $\times$ | \times | 叉乘 |
| $\cdot$  | \cdot  | 点乘 |
| $\ast$   | \ast   | 星乘 |
| $\div$   | \div   |      |
| $\pm$    | \pm    | 加减 |
| $\mp$    | \mp    | 减加 |
| $!$      | !      | 阶乘 |

### 比较运算符

| 预览                   | 公式                 | 说明      |
| -------------------- | ------------------ | ------- |
| $=$                  | =                  |         |
| $\ne$                | \ne                | 与\neq相同 |
| $\neq$               | \neq               |         |
| $\equiv$             | \equiv             |         |
| $\not\equiv$         | \not\equiv         |         |
| $\doteq$             | \doteq             |         |
| $\doteqdot$          | \doteqdot          |         |
| $\overset{force}{=}$ | \overset{force}{=} |         |
| $:=$                 | :=                 |         |
 


#### 矩阵与多行列式 Matrices & Multilines
 