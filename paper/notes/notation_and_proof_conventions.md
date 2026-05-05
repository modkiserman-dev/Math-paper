# Notation and Proof Conventions

This note summarizes the notation and proof conventions to preserve when editing
`paper/main.tex`. It is based on:

- `selberg_delange_transfer_note_v2.md`
- `selberg_delange_transfer_note_v3_addendum.md`

## Core Objects

Use the following notation consistently:

\[
D(x):=\sum_{n\le x} d(n).
\]

\[
P(x):=\sum_{i\ge1}(i+1)\pi(x^{1/i}).
\]

\[
T_j(x):=\sum_{n\le x} d(n)\binom{\omega(n)}{j}.
\]

\[
R(x):=\sum_{j\ge2}(-1)^j(j-1)T_j(x).
\]

The exact identity is

\[
D(x)=1+P(x)+R(x).
\]

Equivalently,

\[
D(x)
=1+\sum_{i\ge1}(i+1)\pi(x^{1/i})
+\sum_{j\ge2}(-1)^j(j-1)T_j(x).
\]

The coefficient in the final sum is

\[
(-1)^j(j-1),
\]

not \((-1)^j j\).

## Generating Series Notation

The final variable is \(y\), not \(z\). This is a true shift from the earlier
\(z\)-notation, not a simple renaming.

\[
A(x,y):=\sum_{n\le x}d(n)(1+y)^{\omega(n)}.
\]

\[
A(x,y)=\sum_{j\ge0}T_j(x)y^j.
\]

\[
T_j(x)=\frac{1}{j!}\partial_y^j A(x,y)\bigg|_{y=0}.
\]

\[
F(s,y):=\sum_{n\ge1}\frac{d(n)(1+y)^{\omega(n)}}{n^s}.
\]

The Euler product factorization is

\[
F(s,y)=\zeta(s)^{2+2y}H(s,y).
\]

Near \(s=1\), define

\[
G(s,y):=((s-1)\zeta(s))^{2+2y}H(s,y),
\]

so that

\[
F(s,y)=G(s,y)(s-1)^{-2-2y}.
\]

## Local Hankel Decomposition

For the polished proof, use the refined Taylor decomposition:

\[
\frac{G(s,y)}{s}
=a_0(y)+a_1(y)(s-1)+(s-1)^2E_2(s,y).
\]

Then the local contribution should be decomposed as

\[
I_H=a_0(y)J_0+a_1(y)J_1+R_2.
\]

Here

\[
J_0
:=\frac{1}{2\pi i}
\int_{\mathcal H_{\mathrm{loc}}}(s-1)^{-2-2y}x^s\,ds,
\]

\[
J_1
:=\frac{1}{2\pi i}
\int_{\mathcal H_{\mathrm{loc}}}(s-1)^{-1-2y}x^s\,ds.
\]

The central change of variables is

\[
w=(s-1)\log x.
\]

This gives the expected sizes

\[
J_0\sim \frac{x(\log x)^{1+2y}}{\Gamma(2+2y)},
\]

\[
J_1\sim \frac{x(\log x)^{2y}}{\Gamma(1+2y)}.
\]

The local remainder recorded in the addendum is

\[
R_2=O\bigl(x(\log x)^{2\operatorname{Re}(y)-1}\bigr).
\]

Do not claim the small circle in the Hankel integral is negligible for
\(\alpha\approx2\) without justification. Use analytic continuation or subtract
enough Taylor terms.

## Error-Term Status

The transfer notes do not finalize a single theorem-level global error term.
They record the decomposition

\[
A(x,y)=I_H+I_{\mathrm{top}}+I_{\mathrm{bot}}+I_{\mathrm{left}}
+E_{\mathrm{Perron}}.
\]

The available nonlocal bounds from the notes are

\[
I_{\mathrm{top}}+I_{\mathrm{bot}}
=O\bigl(x^cT^{B-1}\bigr),
\]

\[
I_{\mathrm{left}}=O\bigl(x^{1-\delta}T^B\bigr),
\]

with \(B<1\) in the fixed-strip setup.

The Perron truncation error must be supplied from the exact Perron theorem used
in the final writeup. Do not present the global error as finalized until this
bookkeeping is made explicit.

## Current Draft Caution

The current `main.tex` uses a de la Vallee Poussin zero-free-region setup with
\[
T=\exp(\sqrt{\log x})
\]
and an exponent

\[
B=(2+2\eta)\left(\frac18+\varepsilon\right)+2\eta C_{\arg}.
\]

Therefore

\[
\inf B=\frac14,
\]

but \(B\) has no minimum under \(\eta>0\) and \(\varepsilon>0\).

Any argument requiring \(B<c_0/2\) needs more than \(c_0\ge 1/2\). It requires

\[
c_0> \frac12
\]

or a sharper growth estimate that lowers the infimum of \(B\).
