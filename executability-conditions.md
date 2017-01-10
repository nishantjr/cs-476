Well founded
: Set, partial order has a least element in the set

Substitution
: A substitution takes a variable to a term of the same sort.
: Given an order-sorted signature $\Sigma$ with set of sorts S and given
  S-indexed families of variables $X = \{X_s\}_{s\in S}, Y = \{Y_s\}_{s\in S}$,
  a substitution is an S-indexed family of functions: $\theta : X
  {\to_{R/B}^{*}}
  T_{\Sigma(Y)}$


### Executability conditions

For $(\Sigma, B, R)$,

1. No extra variables on the right
2. sort decreasingness
3. Confluence
4. Terminates
5. Conditions on $B$
  - B-Matching algorithm
  - Variables of $B$ at kind level
  - Equations in B should be pre-regular
6. $R$ should be sufficiently complete w.r.t. $\omega$, the set of ctors.

sort-decreasingness
: For all transform rules $t\to t'$, and substitutions $\theta$, $t\theta : S
  \Rightarrow t'\theta : s$ (the sort after applying the rule is the same as
  before for all substitutions).

Determinism / Confluence
: Rewrite theory $(\Sigma B, R)$ is confluent if $\forall t \in \bigcup
  T_{\Sigma(Y)}, t {\to_{R/B}^{*}} u,$ and $t {\to_{R/B}^{*}} v$, then there is a term $w \in \bigcup
  T_{\Sigma(Y)}$ such that $u {\to_{R/B}^{*}} w$ and $v {\to_{R/B}^{*}} w$
  rewrite a term, there are rewrite rules such that the final term is the same

  $R$ is ground confluent modulo $B$ if this holds for $\bigcup T_{\Sigma}$
  but not $\bigcup T_{\Sigma(Y)}$

Joinable ($t \downarrow t'$)
: $t$ and $t'$ are joinable iff $\exists w \in \bigcup T_{\Sigma(Y)}$, such that $t {\to_{R/B}^{*}} w$ and $t' {\to_{R/B}^{*}} w$.

Terminating or strongly normalizing
: $(\Sigma, B, R)$ is strongly terminating if ${\to_{R/B}^{*}}$ is well founded.  
: Every sequence of rewrites terminates


Weakly terminating $t\to^!_{E/B}$
: for any $t \in \bigcup T_{\Sigma(Y)}$ has a **R/B-normal form**.
: $\exists v \in \bigcup T_{\Sigma(Y)} : t {\to_{R/B}^{*}} v, \nexists w \in
\bigcup T_{\Sigma(Y)} : v {\to_{R/B}} w$.
: if for all terms, at least one sequence of rewrites terminates.

B-Preregular
: For any $[t]_B$, a set of elements equivalent by $B$, all terms in $[t]_B$
  have a least sort, that is $\{s \in S | t' \in [t]_B, t' : s \}$ has a minimum
  element.

$B$-matching algorithm
: Given two terms $t$ and $t'$, an algorithm that gives a complete set of
  substitutions, such that $t\theta =_B t'$, or fails if no substitution exists.
  If there is such a substitution, then $t$ and $t'$ beta match.

Normal Form
: For $t \in \bigcup T_{\Sigma(Y)}$, if $t {\to_{R/B}^{*}} v$ and $\nexists w
\in \bigcup T_{\Sigma(Y)}$, such that $v {\to_{R/B}} w$ then $v$ is the normal
form of $t$

Canonical form $can_{E/B}(t)$
: If there is  a unique normal form for a term $t$, then this is called it's
canonical form.

Sufficient Completeness
: Given Rewrite theory $(\Sigma, B, R)$, $\Omega \subseteq \Sigma$ with the same
sorts/subsorts. Then $R$ is **sufficiently complete modulo B** w.r.t. 
$\Omega$, iff for each $t \in T_{\Sigma,s}, \exists t' \in T_{\Omega,s}$,
such that $t {\to_{R/B}^{!}} t'$.



---

Locally confluent
: $t \to_{R/B} u$ and $t {\to_{R/B}^{*}}_{R/B} v$, then $u \downarrow_{R/B} v$.
: If $t$ can be rewritten to two different terms, $u, v$, then those can be
  rewritten to the same term.
