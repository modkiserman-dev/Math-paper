# Addendum: Explicit Error Terms and What Was/Was Not Fixed

This addendum clarifies the error terms in the transfer note.
It should be read together with `selberg_delange_transfer_note_v2.md`.

## 1. Short answer

The previous transfer note **did include some explicit error terms**, but it **did not fully pin down one single final global error formula** for the whole theorem.

What *was* made explicit in the conversation:

1. the local Hankel remainder
\[
R_2=O\bigl(x(\log x)^{2\Re(y)-1}\bigr),
\]
2. the horizontal contour contributions
\[
I_{\mathrm{top}}+I_{\mathrm{bot}}\ll x^c T^{B-1},
\]
for an exponent \(B<1\) coming from the growth estimate on \(F(s,y)\) along the strip,
3. the left vertical contribution
\[
I_{\mathrm{left}}\ll x^{1-\delta}T^B,
\]
4. the fact that the Perron truncation error must be included and absorbed into the final error after choosing \(T=T(x)=x^\theta\).

What was **not** completely frozen in the conversation:

- one single final theorem-level error term with a fixed exponent,
- the exact Perron truncation error formula, because that depends on which version of Perron's formula is chosen and how it is normalized,
- the final bookkeeping after combining the contour estimates, the local remainder, and the truncation term.

So the honest status is:

- **local error terms were explicit**,
- **global final error was not fully finalized**.

## 2. Error decomposition currently available from the discussion

We had
\[
A(x,y):=\sum_{n\le x} d(n)(1+y)^{\omega(n)}
\]
and a contour deformation of the truncated Perron integral giving
\[
A(x,y)=I_H+I_{\mathrm{top}}+I_{\mathrm{bot}}+I_{\mathrm{left}}+E_{\mathrm{Perron}},
\]
where:

- \(I_H\) is the local Hankel contribution around \(s=1\),
- \(I_{\mathrm{top}},I_{\mathrm{bot}}\) are the upper and lower horizontal pieces,
- \(I_{\mathrm{left}}\) is the left vertical piece,
- \(E_{\mathrm{Perron}}\) is the truncation error from the finite-length Perron formula.

### 2.1 Local Hankel decomposition

Inside the local Hankel piece, after writing
\[
\frac{G(s,y)}{s}=a_0(y)+a_1(y)(s-1)+(s-1)^2E_2(s,y),
\]
we obtained
\[
I_H=a_0(y)J_0+a_1(y)J_1+R_2,
\]
with
\[
J_0=\frac{1}{2\pi i}\int_{\mathcal H_{\mathrm{loc}}}(s-1)^{-2-2y}x^s\,ds,
\]
\[
J_1=\frac{1}{2\pi i}\int_{\mathcal H_{\mathrm{loc}}}(s-1)^{-1-2y}x^s\,ds,
\]
\[
R_2=\frac{1}{2\pi i}\int_{\mathcal H_{\mathrm{loc}}}E_2(s,y)(s-1)^{-2y}x^s\,ds.
\]

The explicit local remainder estimate discussed was
\[
\boxed{R_2=O\bigl(x(\log x)^{2\Re(y)-1}\bigr).}
\]

Also,
\[
J_0\sim \frac{x(\log x)^{1+2y}}{\Gamma(2+2y)},
\qquad
J_1\sim \frac{x(\log x)^{2y}}{\Gamma(1+2y)}.
\]

Hence locally,
\[
I_H
=
H(1,y)\frac{x(\log x)^{1+2y}}{\Gamma(2+2y)}
+
a_1(y)\frac{x(\log x)^{2y}}{\Gamma(1+2y)}
+O\bigl(x(\log x)^{2\Re(y)-1}\bigr),
\]
at the level discussed in the conversation.

## 3. Horizontal contour errors

For the upper and lower horizontal pieces, we parameterized
\[
s=\sigma\pm iT,
\qquad \sigma_0\le \sigma\le c,
\qquad \sigma_0=1-\delta,
\]
and used:

- \(|x^s|=x^\sigma\le x^c\),
- \(|s|\asymp T\),
- a strip estimate \(|F(\sigma+iT,y)|\ll T^B\) with \(B<1\),
- horizontal length \(c-\sigma_0\asymp 1\).

This gave
\[
|I_{\mathrm{top}}|+|I_{\mathrm{bot}}|\ll x^c T^{B-1}.
\]
So explicitly:
\[
\boxed{I_{\mathrm{top}}+I_{\mathrm{bot}}=O\bigl(x^c T^{B-1}\bigr).}
\]

This is the contour error that tends to zero as \(T\to\infty\), provided \(B<1\).

## 4. Left vertical contour error

For the left vertical piece with
\[
s=\sigma_0+it,
\qquad -T\le t\le T,
\qquad \sigma_0=1-\delta,
\]
we used
\[
|x^s|=x^{\sigma_0}=x^{1-\delta},
\]
and the same type of strip estimate
\[
|F(\sigma_0+it,y)|\ll (|t|+2)^B.
\]
This yielded
\[
|I_{\mathrm{left}}|
\ll x^{1-\delta}\int_{-T}^{T}\frac{(|t|+2)^B}{|\sigma_0+it|}\,dt
\ll x^{1-\delta}T^B.
\]
So explicitly:
\[
\boxed{I_{\mathrm{left}}=O\bigl(x^{1-\delta}T^B\bigr).}
\]

This is generally **not** something that vanishes merely by sending \(T\to\infty\). Instead, one chooses
\[
T=x^\theta
\]
with
\[
\theta<\frac{\delta}{B},
\]
so that
\[
x^{1-\delta}T^B=x^{1-\delta+\theta B}=o(x).
\]
This makes the left vertical term smaller than the main term.

## 5. Perron truncation error: status

This is the one part that was **not frozen into a single explicit formula** in the conversation.

The conversation repeatedly treated the truncated Perron formula schematically as
\[
A(x,y)=\frac{1}{2\pi i}\int_{c-iT}^{c+iT}F(s,y)\frac{x^s}{s}\,ds+E_{\mathrm{Perron}},
\]
and then said that \(E_{\mathrm{Perron}}\) should be combined with the other nonlocal pieces after choosing \(T=T(x)\).

However, we did **not** finally choose and record one canonical explicit bound of the form
\[
E_{\mathrm{Perron}} \ll \cdots
\]
with all conditions spelled out.

This depends on which exact version of Perron's formula is invoked. In a polished writeup, you should choose one standard statement and then quote its error term explicitly.

So the honest notation is:
\[
\boxed{E_{\mathrm{Perron}}\text{ was acknowledged, but not finally pinned down by one explicit formula in the discussion.}}
\]

## 6. Current best “explicit” theorem-level formula available from the discussion

What the conversation currently justifies at a structural level is
\[
A(x,y)
=
H(1,y)\frac{x(\log x)^{1+2y}}{\Gamma(2+2y)}
+
a_1(y)\frac{x(\log x)^{2y}}{\Gamma(1+2y)}
+
E_{\mathrm{global}}(x,y),
\]
where
\[
E_{\mathrm{global}}(x,y)
=
R_2+I_{\mathrm{top}}+I_{\mathrm{bot}}+I_{\mathrm{left}}+E_{\mathrm{Perron}}.
\]

With the discussion as it stands, the explicit known pieces are
\[
R_2=O\bigl(x(\log x)^{2\Re(y)-1}\bigr),
\]
\[
I_{\mathrm{top}}+I_{\mathrm{bot}}=O\bigl(x^cT^{B-1}\bigr),
\]
\[
I_{\mathrm{left}}=O\bigl(x^{1-\delta}T^B\bigr),
\]
and \(E_{\mathrm{Perron}}\) remains to be supplied from the chosen Perron theorem.

So the safest fully honest summary is
\[
\boxed{
E_{\mathrm{global}}(x,y)
=
O\bigl(x(\log x)^{2\Re(y)-1}\bigr)
+
O\bigl(x^cT^{B-1}\bigr)
+
O\bigl(x^{1-\delta}T^B\bigr)
+
E_{\mathrm{Perron}}.
}
\]

After choosing \(T=x^\theta\) and inserting the chosen explicit Perron truncation error, one can optimize or simplify this further.

## 7. What should be done in the thesis draft

To make the thesis self-contained and explicit:

1. **Choose a specific Perron formula statement** from a standard source.
2. Record its error term exactly.
3. State the contour decomposition as
   \[
   A(x,y)=I_H+I_{\mathrm{top}}+I_{\mathrm{bot}}+I_{\mathrm{left}}+E_{\mathrm{Perron}}.
   \]
4. State the local result
   \[
   I_H
   =H(1,y)\frac{x(\log x)^{1+2y}}{\Gamma(2+2y)}
   +a_1(y)\frac{x(\log x)^{2y}}{\Gamma(1+2y)}
   +O\bigl(x(\log x)^{2\Re(y)-1}\bigr).
   \]
5. Then append a separate proposition/lemma controlling the nonlocal terms.
6. Only after that combine them into one final theorem.

## 8. Bottom line for the user’s question

No: the previous transfer note did **not** completely freeze the global error into one fully explicit formula.

Yes: it **did** contain and discuss explicit error pieces, namely
\[
R_2=O\bigl(x(\log x)^{2\Re(y)-1}\bigr),
\]
\[
I_{\mathrm{top}}+I_{\mathrm{bot}}=O\bigl(x^cT^{B-1}\bigr),
\]
\[
I_{\mathrm{left}}=O\bigl(x^{1-\delta}T^B\bigr).
\]

The only missing explicit ingredient is the exact Perron truncation error from the specific Perron theorem to be quoted in the final writeup.
