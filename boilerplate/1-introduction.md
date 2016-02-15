# Introduction

This is the introduction ^[Also, here is a footnote]. Here you can write what
your document will be about. This is the best thing ever [@Meyer2000
@Codishetal2000].

## Math

Here is inline math \(1+1=2\) and a math block:

\[
\theta = 0
\quad \Rightarrow \quad
\sin^{2}\theta = 0
\]{#eq:math-example}

## Code

Here is a code block

```{#lst:code-example .ruby .numberLines caption="Ruby code example"}
array = %w(1 2 3)
squared = array.map{|n| n*n}
puts squared
```

## Image

Here is a figure

![Ginger the Cat by Henry Riley](images/cat.jpg){#fig:cat}

## Table

Create tables with captions like so:

| a | b | c |
|---|---|---|
| 1 | 2 | 3 |
| 4 | 5 | 6 |{#tbl:table-example}

: Example table

## Crossreferencing

You can also reference math [@eq:math-example], code [@lst:code-example],
figures [@fig:cat].

## Lists

_References_ is by default added in the `references.md` file. However you can
also add a lists of figures, tables and/or listings.

\listoffigures

\listoftables

\listoflistings
