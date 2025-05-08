---
title: "Visualizing OEIS A000108 - Catalan Numbers - Draft"
author: Cong Le
created: 2025-05-08
version: 1.0
---


# Visualizing OEIS A000108 - Catalan Numbers - Draft

> **Source Attribution:**
>
> This document incorporates or adapts material from:
> - **The Online Encyclopedia of Integer Sequences** ([https://oeis.org/](https://oeis.org/))
> - Specific sequence: [OEIS A000108](https://oeis.org/A000108)
> - © The OEIS Foundation Inc.
>
> **License:**
> 
> - **OEIS-derived content** (any mathematical data, structure, text, or visuals based on OEIS): **CC BY-SA 4.0**
> - If you adapt/redistribute these portions, you **must** provide attribution as above and license your derivative work under the same terms.
> - **Original diagram source code** (e.g., Mermaid, PlantUML, or script syntax BY CONG LE, not including OEIS math/data): **MIT License**, unless otherwise stated.
> - If you reuse just the code itself for unrelated subjects, **MIT** applies.




Below is a collection of *strategically designed Mermaid diagrams* elaborating the core structures, recurrences, combinatorial interpretations, formulas, and the rich mathematical framework of the **Catalan numbers** as distilled from [the original documentation](https://oeis.org/A000108).

---

## 1. Catalan Number Sequence and Fundamental Formulae

```mermaid
---
title: "Catalan Number Sequence and Fundamental Formulae"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    A[Definition] -->|Main Formula| B["C(n) = binomial(2n, n) / (n + 1)"]
    A -->|Alternative| B2["C(n) = (2n)! / (n! * (n+1)!)"]
    A -->|Generating Function| C["A(x) = (1 - sqrt(1 - 4x)) / (2x)"]
    A -->|Recursive| D["C(0) = 1; C(n) = Σ_{k=0}^{n-1} C(k)·C(n-1–k)"]
    A -->|Functional Equation| E["A(x) = 1 + x·A(x)^2"]
    A -->|Asymptotics| F["C(n) ~ 4^n / [sqrt(π·n)·(n+1)]"]
    A -->|Recurrence 2| G["C(n) = 2·(2n-1)·C(n-1)/(n+1)"]
    D -.->|Offset| O["OFFSET 0,3"]
    B -.->|First values| V["1, 1, 2, 5, 14, 42, ..."]
```

---

## 2. Tree of Major Combinatorial Interpretations

```mermaid
---
title: "Tree of Major Combinatorial Interpretations"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%{
  init: {
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
mindmap
root(("Catalan Numbers<br/>C(n)"))
    Bracketings("Bracketings")
      Ways_to_parenthesize_terms["Ways to parenthesize (n+1) terms"]
      Binary_tree_structures["Binary tree structures"]
    Dyck_Paths("Dyck Paths")
      Lattice_paths_with_steps["Lattice paths with steps (1,1)/(1,-1) from (0,0) to (2n,0)"]
      Never_go_below_the_axis["Never go below the axis"]
    Noncrossing_Partitions("Noncrossing Partitions")
      Count_of_noncrossing_set_partitions["Count of noncrossing set partitions"]
      Genus_0_partitions["Genus-0 partitions"]
    Ordered_Trees("Ordered Trees")
      Plane_rooted_trees["Plane rooted trees with n non-root nodes"]
      Plane_bushes_Catalan_trees["Plane bushes /<br/> Catalan trees"]
    Polygon_Triangulations("Polygon Triangulations")
      Ways_to_triangulate_a_convex["Ways to triangulate a convex (n+2)-gon"]
    Nonintersecting_Chords("Nonintersecting Chords")
      Ways_to_connect_2n_points["Ways to connect 2n points on a circle with n noncrossing chords"]
    Permutations("Permutations")
      Number_of_stack_sortable_permutations["Number of stack-sortable permutations<br/>(231-avoiding)"]
      Length["Length = depth permutations"]
    Binary_Sequences("Binary Sequences")
      Binary_words["Binary words:<br/>in any prefix, #ones ≥ #zeros, length=2n, n ones"]
    Young_Tableaux("Young Tableaux")
      Number_of_standard_tableaux["Number of standard tableaux of shape (n,n)"]
    Other("Other")
      Motzkin_paths["Motzkin paths<br/>(special cases)"]
      Catalan_monoid_transformations["Catalan monoid transformations"]
      Polyominoes_Schubert_calculus_operads["Polyominoes, Schubert calculus, operads, etc."]
      
```



---

## 3. Core Recursion and Self-Convolution

```mermaid
---
title: "Core Recursion and Self-Convolution"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart LR
    X["C(0) = 1"] --> Y["C(n) = Σ_{k=0}^{n-1} C(k)·C(n–1–k)"]
    Y -.-> Z["This is also:<br/> (C * C)[n–1], i.e., Catalan# = Catalan⨂Catalan <br/>(shifted left)"]
    X -->|alternative| Y2["C(n) = 2·(2n–1)·C(n–1)/(n+1)"]
    Y2 -.->|efficient computation| Y
    
```

---

## 4. Generating Functions and Continued Fractions

```mermaid
---
title: "Generating Functions and Continued Fractions"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    A1["A(x) = (1 – sqrt(1–4x)) / (2x)"] --> B1["A(x) = 1 + x·A(x)^2"]
    B1 --> C1["Continued fraction:<br/> A(x) = 1/(1 - x/(1 - x/(1 - ... )))"]
    B1 --> D1["A(x) = Σ_{n=0}^∞ C(n)x^n"]
    D1 -.-> E1["Related to Motzkin, Fine, Fibonacci numbers via composition transformations"]
    
```

---

## 5. Many Faces of Catalan (Object Mappings)

```mermaid
---
title: "Many Faces of Catalan (Object Mappings)"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    A("Binary Trees <br/> (n nodes)") -- bijection --> B("Parenthesis Insertions <br/> (n+1 terms)")
    A -- bijection --> C("Dyck Paths <br/> (2n steps)")
    C -- bijection --> D("Noncrossing Chords <br/> (2n points on circle)")
    D -- bijection --> E("Triangulations <br/> (n+2-gon)")
    E -- bijection --> F("Stack-sortable permutations <br/> (231-avoiding)")
    C -- bijection --> G("Binary sequences with prefix property")
    D -- bijection --> H("Noncrossing partitions <br/> (n elements)")
    F -- bijection --> I("Standard Young Tableaux (n,n)")
    E -- bijection --> J("Planted plane trees <br/> (plane bushes)")
    
```

---

## 6. Algorithmic Formulas Collage

```mermaid
---
title: "Algorithmic Formulas Collage"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    Start(("n"))
    Start -->|explicit formula| A["C(n) = binomial(2n, n)/(n+1)"]
    Start -->|recursive| B["C(0) = 1; <br/>C(n) = Σ_{k=0}^{n-1} C(k)·C(n–1–k)"]
    Start -->|efficient recursion| C["C(n) = 2·(2n–1)·C(n–1)/(n+1)"]
    Start -->|product form| D["C(n) = Π_{k=2}^{n} (1 + n/k)"]
    A -.-> E["Generating Function:<br/>A(x) = (1–sqrt(1–4x))/(2x)"]
    E -.-> F["Quadratic:<br/> A(x) = 1 + x·A(x)^2"]
    E -.-> G["Continued Fraction:<br/> 1/(1–x/(1–x/(1–x/(...))))"]
    E -.-> H["Asymptotics:<br/> C(n) ~ 4^n/(sqrt(πn)·(n+1))"]
    
```

---

## 7. Lattice Paths: Interpretation of Dyck Paths

```mermaid
---
title: "Lattice Paths: Interpretation of Dyck Paths"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    S["Start<br/>(0,0)"] -->|step| S1(("Step +1,+1"))
    S -->|step| S2(("Step +1,-1"))
    S1 & S2 --> E["End<br/>(2n,0)"]
    Z["Constraint:<br/>Never go below x-axis"]
    S -.-> Z
    
    E -->|count of such paths| F["C(n):<br/> Catalan number"]
    
```

---

## 8. Tree of Notable Properties and Further Connections

```mermaid
---
title: "Tree of Notable Properties and Further Connections"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%{
  init: {
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
mindmap
  root(("Catalan Numbers Properties"))
    Algebraic("Algebraic")
      Primitive_for_many_sequences["Primitive for many sequences"]
      Hankel_transform["Hankel transform gives the all 1's sequence"]
      Roots_of_combinatorial_generating_functions["Roots of combinatorial generating functions"]
    Arithmetical("Arithmetical")
      Parity["Parity:<br/> C(n) odd iff n=2^k -1"]
      Prime_divisibility_rules["Prime divisibility rules for C(n)"]
      Only_C_2_and_C_3_are_prime["Only C(2)=2 and C(3)=5 are prime"]
    Transformations("Transformations")
      Self_convolution_shifts_left["Self-convolution shifts left"]
      Inverse_Euler["Inverse Euler:<br/> relates to Lyndon words"]
      Binomial_Motzkin_Fine numbers["Binomial, Motzkin, Fine numbers via transforms"]
    Analytical("Analytical")
      Integral_rep["Integral rep:<br/> (1/(2π)) ∫ x^n·sqrt((4-x)/x) dx"]
      E_g_f["E.g.f., hypergeom, Bessel function"]
      Asymptotic["Asymptotic:<br/>exponential growth, limit ratio 4"]
    Enumerative("Enumerative")
      Noncrossing_and_genus_0_partitions["Noncrossing and genus-0 partitions"]
      Motzkin_Dyck_Narayana_numbers_connections["Motzkin, Dyck, Narayana numbers connections"]
      231_avoiding_132_avoiding_permutations["231-avoiding,<br/> 132-avoiding permutations"]
      Non_associative_product_trees["Non-associative product trees<br/>(Wedderburn-Etherington)"]
      Jones_monoid_Catalan_monoid["Jones monoid,<br/> Catalan monoid"]
    Geometry("Geometry")
      Convex_polygon_triangulations["Convex polygon triangulations"]
      Grassmannian_degree_connections["Grassmannian degree connections"]
      Friezes_Schubert_calculus["Friezes, Schubert calculus"]
    Other("Other")
      Probability_in_random_walks["Probability in random walks"]
      Stack_sorting_lucky_Stirling_permutations["Stack-sorting,<br/> lucky Stirling permutations"]
      Permutations_with_particular_order_ideals["Permutations with particular order ideals"]
      
```



---

## 9. Formulas and Generating Function Interrelationships

```mermaid
---
title: "Formulas and Generating Function Interrelationships"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    A[("A(x)")]
    A -->|Quadratic| B["A(x) = 1 + x*A(x)^2"]
    A -->|Continued Fraction| C["A(x) = 1/(1 - x/(1 - x/(1 - ...)))"]
    A -->|functional equations| D["A(x) = 1/sqrt(1 - 4x) * A(-x/(1-4x))"]
    A -->|Hypergeom| F["A(x) = 2F1(1/2,1;2;4x)"]
    A -.->|Bessel Egf| E["Egf = exp(2x)(I_0(2x) - I_1(2x))"]
    D -.->|Compositional Inverse| G["x·A(x^3) = x + (x·B(x))^2"]
    
```

---

## 10. Meta-Structure: Catalan in Research and Mathematics

```mermaid
---
title: "Meta-Structure: Catalan in Research and Mathematics"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart TD
    C["Applications"]
    C --> C1("Combinatorics<br/>(Bracketings, Trees, Paths)")
    C --> C2("Algebra<br/>(Associativity, Monoid Theory)")
    C --> C3("Geometry<br/>(Polygon Triangulation, Grassmannians)")
    C --> C4("Computer Science<br/>(Parsing, Data Structures, Stack-sortable Permutations)")
    C --> C5("Probability<br/>(Random Walks, Ballot Problems)")
    C --> C6("Physics<br/>(Quantum Field Theory, Feynman Diagrams)")
    C --> C7("Other<br/>(Friezes, Knot Theory, Operads, Polyominoes)")
    C -.-> D[References/Links:<br/>Stanley, Comtet, Conrad, Guy, Knuth, Riordan, etc.]
    
```

---

## 11. Timeline & Name Origin

```mermaid
---
title: "Timeline & Name Origin"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'timeline': { 'htmlLabels': false},
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#145A32',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
timeline
    title The History and Naming of Catalan Numbers
    1751: Euler computes triangulations (polygon divisions, recursion for C(n+2))
    1758: Segner's combinatorial problem formulation with C(n)
    1838: Catalan poses triangulation question, independently discovers numbers
    1870: Schröder (parenthesis, Dyck words)
    1882: Cayley (binary trees)
    1948: Riordan uses "Catalan number" in Mathematical Reviews
    1968: Riordan's Combinatorial Identities book cements term
    2014: Pak's historical studies provide naming clarity
```

---

## 12. Asymptotics, Limits, and Growth

```mermaid
---
title: "Asymptotics, Limits, and Growth"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart LR
    Start["C(n)"]
    Start -->|Limit Ratio| L1["lim_{n→∞} C(n)/C(n–1) = 4"]
    Start -->|Asymptotics| L2["C(n) ~ 4^n/(sqrt(π n) (n+1))"]
    Start -->|Primality| L3["Only C(2)=2, C(3)=5 are prime"]
    Start -->|Oddness| L4["C(n) is odd iff n=2^k–1"]
    
```

---

## 13. Algorithm Implementations (Overview)

```mermaid
---
title: "Algorithm Implementations (Overview)"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Available curve styles include the following keywords:
%% basis, bumpX, bumpY, cardinal, catmullRom, linear, monotoneX, monotoneY, natural, step, stepAfter, stepBefore.
%%{
  init: {
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
flowchart LR
    S["Inputs: n"]
    S -->|Direct| F1["C(n) = binomial(2n, n) / (n+1)"]
    S -->|Recursive| F2["C(0)=1; for k=1..n: C(n) = Σ_{i=0}^{n-1} C(i)·C(n-1-i)"]
    S -->|Iterative| F3["C(n) = 2·(2n–1)·C(n–1)/(n+1)"]
    F1 & F2 & F3 -->|Implementations| T1["Maple, Mathematica, Pari, Python, Haskell, Sage"]
```

---

## 14. Catalan in the "Universe" of OEIS and Cross-References

```mermaid
---
title: "Catalan in the 'Universe' of OEIS and Cross-References"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: dagre
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%{
  init: {
    'erDiagram': { 'htmlLabels': true },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '15px'
    }
  }
}%%
erDiagram
    "CatalanNumbers (A000108)" ||--o| "MotzkinNumbers (A001006)" : BinomialTransform
    "CatalanNumbers" ||--o| "CentralBinomial (A000984)" : "n-th term is CB(n)/(n+1)"
    "CatalanNumbers" ||--o| "FineNumbers (A000957)" : Convolution
    "CatalanNumbers" ||--o| "Narayana (A001263)" : RowSum
    "CatalanNumbers" ||--o| "Wedderburn-Etherington (A001190)" : NonassocProducts
    "CatalanNumbers" ||--o| "SchroederNumbers (A001003)" : Generalization
    "CatalanNumbers" ||--o| "PolygonDissections (A000207)" : Triangulations
```

---

## 15. "Catalan Number World" (Summary Mindmap)

```mermaid
---
title: "Catalan Number World"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%{
  init: {
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#F8B229',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
mindmap
root(("Catalan Numbers"))
    Sequence("Sequence")
      Explicit_Formula["Explicit Formula"]
      Generating_Function["Generating Function"]
      Recursions["Recursions"]
    Combinatorics("Combinatorics")
      Tree_Structures["Tree Structures"]
      Paths_and_Walks["Paths & Walks"]
      Parenthesizations["Parenthesizations"]
      Polygon_Triangulations["Polygon Triangulations"]
      Chord_Diagrams["Chord Diagrams"]
      Set_Partitions_and_Tableaux["Set Partitions & Tableaux"]
    Algebra_and_Arithmetic("Algebra & Arithmetic")
      Parity_and_Primality["Parity & Primality"]
      Prime_Divisors["Prime Divisors"]
      Congruence_Relations["Congruence Relations"]
    Transformations("Transformations")
      Hankel["Hankel"]
      Euler_Binomial["Euler/Binomial"]
      Self_Convolution["Self-Convolution"]
    Applications("Applications")
      Sorting_Parsing["Sorting, Parsing"]
      Random_Walk_Probabilities["Random Walk Probabilities"]
      Quantum_Field_Theory["Quantum Field Theory"]
      Algebraic_Geometry["Algebraic Geometry<br/>(e.g. Grassmannians)"]
      Operads_Semigroups["Operads,<br/> Semigroups"]
    Connections("Connections")
      OEIS_Sequences["OEIS Sequences"]
      Physics_CS_Geometry["Physics, CS, Geometry"]
      Probability_Number_Theory["Probability,<br/> Number Theory"]
    Growth("Growth")
      Asymptotic_Analyses["Asymptotic Analyses"]
      
```


---


By connecting recursive, enumerative, algebraic, and analytic frameworks, these diagrams collectively showcase the **beauty, ubiquity, and depth of the Catalan numbers**—linking explicit formulas, tree and path interpretations, partition lattice structure, transformations, and real-world mathematical applications.




---

> **License and Attribution**
> - Mathematical data and exposition adapted from **The Online Encyclopedia of Integer Sequences** (<https://oeis.org/>), [OEIS sequence A000108](https://oeis.org/A000108), © OEIS Foundation Inc., licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) [![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-sa/4.0/).
> - Legal details in [LICENSE-CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0) and at [Creative Commons official site](https://creativecommons.org/licenses/by-sa/4.0/).
> - Diagram and explanatory code © 2025 Cong Le, **MIT License** [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) (for code **only**)- Full text in [LICENSE](LICENSE) file.
> - If you adapt, redistribute, or make derivative works involving *OEIS-based content*, you must retain this notice and apply **CC BY-SA 4.0**.

---

