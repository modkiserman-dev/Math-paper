# Math Paper Draft Guide

This repository contains a working LaTeX draft of a paper on a combinatorial
decomposition of the divisor summatory function and fixed-\(j\)
Selberg--Delange asymptotics.

The purpose of this README is not to replace the paper. It records the notation,
definitions, and writing conventions that should be preserved when editing the
draft.

## Main Files

- `paper/main.tex`: main LaTeX source.
- `paper/build/main.pdf`: compiled PDF output, generated locally and not tracked
  by git.
- `paper/README.md`: build instructions.
- `paper/notes/notation_and_proof_conventions.md`: detailed notation and proof
  conventions.
- `paper/notes/selberg_delange_transfer_note_v2.md`: original transfer note.
- `paper/notes/selberg_delange_transfer_note_v3_addendum.md`: addendum on error
  terms and unfinished points.

## Project Aim

The paper starts from the divisor summatory function

\[
D(x):=\sum_{n\le x} d(n),
\]

and studies an exact decomposition according to the number of distinct prime
factors. The current analytic target is the fixed-\(j\) asymptotic for

\[
T_j(x):=\sum_{n\le x} d(n)\binom{\omega(n)}{j}.
\]

The fixed-\(j\) analysis is a first step toward understanding the alternating
inclusion--exclusion contribution to \(D(x)\). It does not by itself justify
summing the asymptotics over all \(j\).

## Core Notation

Use the following notation consistently:

\[
d(n)=\tau(n),
\qquad
\omega(n)=\#\{p:p\mid n\},
\qquad
\pi(x)=\#\{p\le x:p\text{ prime}\}.
\]

Define

\[
P(x):=\sum_{i\ge 1}(i+1)\pi(x^{1/i}),
\]

and

\[
R(x):=\sum_{j\ge 2}(-1)^j(j-1)T_j(x).
\]

The exact identity is

\[
D(x)=1+P(x)+R(x),
\]

equivalently

\[
D(x)
=1+\sum_{i\ge 1}(i+1)\pi(x^{1/i})
+\sum_{j\ge 2}(-1)^j(j-1)T_j(x).
\]

The coefficient in the last sum is \((-1)^j(j-1)\). Do not change it to
\((-1)^j j\).

## Generating Function Convention

The final paper should use the \(y\)-shifted convention. Define

\[
A(x,y):=\sum_{n\le x}d(n)(1+y)^{\omega(n)}.
\]

Then

\[
A(x,y)=\sum_{j\ge 0}T_j(x)y^j,
\]

and therefore

\[
T_j(x)=\frac{1}{j!}\partial_y^j A(x,y)\bigg|_{y=0}.
\]

The Dirichlet series associated with this generating function is

\[
F(s,y):=\sum_{n\ge 1}\frac{d(n)(1+y)^{\omega(n)}}{n^s}.
\]

This is the convention to use in the paper. If an older note uses

\[
F(s,z):=\sum_{n\ge 1}\frac{d(n)z^{\omega(n)}}{n^s},
\]

then the relation is \(z=1+y\). This is a shift, not a mere renaming.

In particular, the singular exponent changes by

\[
2z\mapsto 2(1+y)=2+2y.
\]

## Euler Product and Factorization

For \(\operatorname{Re}(s)>1\),

\[
F(s,y)
=\prod_p
\left(
1+(1+y)\left((1-p^{-s})^{-2}-1\right)
\right).
\]

The singularity at \(s=1\) should be isolated as

\[
F(s,y)=\zeta(s)^{2+2y}H(s,y),
\]

where

\[
H(s,y)
:=\prod_p
(1-p^{-s})^{2+2y}
\left(
1+(1+y)\left((1-p^{-s})^{-2}-1\right)
\right).
\]

The factor \(H(s,y)\) is the holomorphic Euler product factor. At \(y=0\),

\[
F(s,0)=\zeta(s)^2,
\qquad
H(s,0)\equiv 1.
\]

## Local Form Near \(s=1\)

Near \(s=1\), define

\[
G(s,y):=((s-1)\zeta(s))^{2+2y}H(s,y).
\]

Then

\[
F(s,y)=G(s,y)(s-1)^{-2-2y}.
\]

The branch behavior should be carried by \((s-1)^{-2-2y}\), while
\(G(s,y)\) should be treated as analytic near \(s=1\).

For the local Hankel contribution, use the refined Taylor decomposition

\[
\frac{G(s,y)}{s}
=a_0(y)+a_1(y)(s-1)+(s-1)^2E_2(s,y).
\]

This leads to

\[
I_H=a_0(y)J_0+a_1(y)J_1+R_2.
\]

The change of variables in the Hankel analysis is

\[
w=(s-1)\log x.
\]

The expected local scales are

\[
J_0\sim \frac{x(\log x)^{1+2y}}{\Gamma(2+2y)},
\qquad
J_1\sim \frac{x(\log x)^{2y}}{\Gamma(1+2y)}.
\]

Do not claim that the small circle in the Hankel contour is negligible for
exponents near \(2\) without a justification. Use analytic continuation or
subtract enough Taylor terms.

## Current Contour Parameter Convention

The current draft uses a single fixed strip parameter \(\delta'\). It no longer
uses separate parameters \(\delta'\) and \(\delta_*\).

The intended choice is

\[
\delta'\in\left(\frac{c_0}{2\log 3},\frac{c_0}{2}\right),
\]

where \(c_0\) is the constant from the de la Vallee Poussin zero-free region.
For \(T\ge 1\), define

\[
\lambda_T:=\frac{c_0}{2\log(T+2)}.
\]

Then

\[
\lambda_T\le \frac{c_0}{2\log 3}<\delta'.
\]

The growth exponent on the nonlocal contour is currently written as

\[
B=B(\delta')
=(2+2\eta)\left(\frac{\delta'}{2}+\varepsilon\right)
+2\eta C_{\arg}.
\]

Since \(B\to\delta'\) as \(\eta,\varepsilon\to0^+\), the choice
\(\delta'<c_0/2\) allows \(B<c_0/2\) after taking \(\eta\) and
\(\varepsilon\) sufficiently small.

## Domain and Branch Rules

The branch of \(\zeta(s)^{2+2y}\) should be discussed only on the chosen
zero-free slit domain \(\mathcal D\), not on the whole vertical strip. Bounds for
\(F(s,y)\) involving this non-integer power must be stated on points of
\(\mathcal D\) actually used by the contour.

The current theorem for \(\arg\zeta(s)\) should be read with the restriction
\(s\in\mathcal D\) and \(|t|\ge 2\).

## Writing Rules for Future Edits

- Keep \(F(s,y)\) for the shifted Dirichlet series using
  \((1+y)^{\omega(n)}\).
- Use \(A(x,y)\) for the corresponding partial-sum generating function.
- Keep \(T_j(x)\) for the coefficient of \(y^j\) in \(A(x,y)\).
- Preserve the exact identity for \(D(x)\) with coefficient
  \((-1)^j(j-1)\).
- Do not present fixed-\(j\) asymptotics as enough to recover \(D(x)\) without
  proving the required cancellation in the \(j\)-sum.
- Do not apply non-integer powers of \(\zeta(s)\) outside the chosen branch
  domain.
- References are intentionally incomplete in the draft and can be filled later.
