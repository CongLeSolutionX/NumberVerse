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
> - **© The OEIS Foundation Inc.**
>
> **License:**
> 
> - **OEIS-derived content** (any mathematical data, structure, text, or visuals based on OEIS): **CC BY-SA 4.0**
> - If you adapt/redistribute these portions, you **must** provide attribution as above and license your derivative work under the same terms.
> - **Original diagram source code** (e.g., Mermaid, PlantUML, or script syntax BY CONG LE, not including OEIS math/data): **MIT License**, unless otherwise stated.
> - If you reuse just the code itself for unrelated subjects, **MIT** applies.


----


The On-Line Encyclopedia of Integer Sequences (OEIS) entry A000108 describes the Catalan numbers. This document provides a comprehensive overview of this fascinating sequence. Below are diagrams illustrating its various facets.


## 1. Overview of Catalan Numbers (A000108)

This mind map provides a high-level overview of the topics covered in the OEIS entry for Catalan numbers.

```mermaid
---
title: "Overview of Catalan Numbers (A000108)"
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
root(("A000108:<br/>Catalan Numbers"))
    Sequence_Values("Sequence Values:<br/>1, 1, 2, 5, 14, 42, 132, ...")
        Offset["Offset:<br/>0,3<br/>(meaning a(0)=1, a(1)=1, a(2)=2, a(3)=5, ...)"]
    Names["Names"]
        Catalan_Numbers["Catalan Numbers"]
        Segner_Numbers["Segner Numbers<br/>(formerly)"]
    Significance("Significance")
        Extensive combinatorial interpretations
        Longest_entry_in_OEIS["Longest entry in OEIS<br/>(highlighting its importance)"]
    Core_Mathematical_Properties("Core Mathematical Properties")
        Formulas
            Binomial_Coefficient_Formula["Binomial Coefficient Formula"]
            Recursive_Formula["Recursive Formula"]
            Generating_Function["Generating Function"]
            Product_Formula["Product Formula"]
            Asymptotic_Expansion["Asymptotic Expansion"]
            Integral_Representation["Integral Representation"]
        Key_Properties["Key Properties"]
            Odd_Catalan_Numbers_Condition["Odd Catalan Numbers Condition"]
            Prime_and_Semiprime_Values["Prime and Semiprime Values"]
            Limit_of_Ratio["Limit of Ratio<br/>C(n)/C(n-1)"]
            Hankel_Transform["Hankel Transform"]
            Relationships_with_other_sequences["Relationships with other sequences"]
    Combinatorial_Interpretations("Combinatorial Interpretations")
        Parenthesization_Schröder_first_problem["Parenthesization Schröder's first problem)"]
        Dyck_Paths["Dyck Paths"]
        Noncrossing_Partitions["Noncrossing Partitions"]
        Rooted_Ordered_Trees["Rooted Ordered Trees"]
        Nonintersecting_Chords["Nonintersecting Chords"]
        Polygon_Triangulations["Polygon Triangulations"]
        Stack_Sortable_Permutations["Stack-Sortable Permutations"]
        Binary_Bracketing["Binary Bracketing"]
        And_many_more["And many more..."]
    Computational_Aspects("Computational Aspects")
        Code_Examples_in_Various_Languages["Code Examples in Various Languages<br/>(Maple, Mathematica, PARI, Python etc.)"]
    OEIS_Entry_Structure("OEIS Entry Structure")
        Comments
        References
        Links
        Formulae
        Examples
        Programs
        Cross-references
        Keywords
        Author
        Status
      
```



---

## 2. Fundamental Formulas for Catalan Numbers

The Catalan numbers, C(n) or a(n) in the OEIS entry, can be defined and calculated through several fundamental formulas.

```mermaid
---
title: "Fundamental Formulas for Catalan Numbers"
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
    A["Catalan Number C(n)"] --> B["Binomial Formula:<br/> C(n) = binomial(2n, n) / (n+1)"]
    A --> C["Recursive Formula:<br/> C(n) = Σ_{k=0}^{n-1} C(k) * C(n-1-k) <br/> (for n ≥ 1, C(0)=1)"]
    A --> D["Generating Function<br/> A(x) = Σ_{n=0}^{∞} C(n)x^n"]
    D --> E["Closed Form:<br/> A(x) = (1 - √(1 - 4x)) / (2x)"]
    D --> F["Functional Equation:<br/> A(x) = 1 + x * A(x)²"]
    A --> G["Product Formula (n≥1):<br/> C(n) = Π_{k=2}^{n} (n+k)/k"]
    A --> H["Alternative Recursion:<br/> C(n) = 2(2n-1)/(n+1) * C(n-1) <br/> (for n ≥ 1, C(0)=1)"]

    subgraph FormulaDetails["Formula Details"]
        B_Detail["Equivalent to:<br/> (2n)! / (n! * (n+1)!)"]
        B --> B_Detail
        C_Base["Base Case:<br/> C(0) = 1"]
        C --> C_Base
        E_Note["Requires series expansion for x → 0 to yield C(0)=1"]
        E --> E_Note
    end
    
```



---

## 3. Key Combinatorial Interpretations Sampler

Catalan numbers appear as the solution to a vast array of counting problems. Here are a few prominent examples:

```mermaid
---
title: "Key Combinatorial Interpretations Sampler"
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
    subgraph Interpretations["Common Combinatorial Interpretations of C(n)"]
        I1["Parenthesization<br/>(Schröder's first problem)"]
        I1_Desc["Number of ways to insert n pairs of parentheses in a word of n+1 letters.<br/>e.g., C(2)=2 for 3 letters: ((ab)c), (a(bc))"]
        I1 --> I1_Desc

        I2["Dyck Paths"]
        I2_Desc["Number of paths from (0,0) to (2n,0) using steps (+1,+1) and (+1,-1),<br/>never going below the x-axis.<br/>e.g., C(2)=2: UUDD, UDUD (U=(+1,+1), D=(+1,-1))"]
        I2 --> I2_Desc

        I3["Noncrossing Partitions"]
        I3_Desc["Number of noncrossing partitions of an n-set.<br/>e.g., C(3)=5 noncrossing partitions of {1,2,3}:<br/>{{1}{2}{3}}, {{12}{3}}, {{1}{23}}, {{13}{2}}, {{123}}"]
        I3 --> I3_Desc

        I4["Rooted Ordered Trees<br/>(Plane Bushes)"]
        I4_Desc["Number of ordered rooted trees with n nodes (not including the root, per entry context for a(n), or n+1 total nodes if root is counted).<br/>Typically: C(n) is number of plane trees with n+1 nodes.<br/>For n=2 (3 nodes total): 2 trees"]
        I4 --> I4_Desc
        I4_Ex1["Tree 1 (n=2):<br/> Root -> (Child1 -> Leaf, Child2 -> Leaf)"]
        I4_Ex2["Tree 2 (n=2):<br/> Root -> (Child1 -> (Grandchild1 -> Leaf))"]
        I4_Desc --> I4_Ex1
        I4_Desc --> I4_Ex2

        I5["Triangulations of a Polygon"]
        I5_Desc["Number of ways to divide a convex (n+2)-gon into n triangles using n-1 non-intersecting diagonals.<br/>e.g., C(2)=2 for a square (4-gon): 2 triangulations"]
        I5 --> I5_Desc

        I6["Binary Bracketing /<br/> Non-associative Products"]
        I6_Desc["Number of ways to apply a binary operation to n+1 factors.<br/>This is C(n). For n=3 (4 factors xxxx):<br/> ((xx)x)x, (x(xx))x, (xx)(xx), x((xx)x), x(x(xx)) correspond to C(3)=5."]
        I6 --> I6_Desc

        I7["Stack-Sortable Permutations"]
        I7_Desc["Number of permutations of [n] that are 231-avoiding (can be sorted using a single stack).<br/>e.g., C(3)=5 for permutations of {1,2,3}:<br/>123, 132, 213, 231 (avoiding), 312, 321 (avoiding) -> (123, 132, 213, 312, 321 if 231-avoiding is the constraint, count of 231-avoiding perms of length n is C(n))"]
        I7_Desc_Note["The OEIS example notes a(n) is for S(n), so C(3) = 5 permutations of {1,2,3} avoid 231: 123, 132, 213, 312, 321."]
        I7_Desc --> I7_Desc_Note
        I7 --> I7_Desc
    end
    
```


---

## 4. Generating Function Relationship: `A(x) = 1 + x * A(x)²`

The recursive nature of many Catalan structures leads directly to the functional equation for its ordinary generating function (o.g.f.).

```mermaid
---
title: "Generating Function Relationship: `A(x) = 1 + x * A(x)²`"
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
    Start["Consider generic Catalan structure S of size n"] --> S_BaseCase{"Is n = 0?"}
    S_BaseCase -- Yes --> Empty_Structure["Empty structure (size 0).<br/>Contribution: 1 (for C(0)x^0 in A(x))"]
    S_BaseCase -- No --> Decompose["Decompose S into: <br/>- A fixed initial element (contribution: x)<br/>- Two smaller Catalan structures S1 and S2 of sizes k and n-1-k"]
    Decompose --> GF_Equation["Sum over all k:<br/> x * (Σ_{k=0}^{n-1} C(k)x^k) * (Σ_{j=0}^{n-1-k} C(j)x^j)"]
    Empty_Structure --> Sum_GF["A(x) = 1 + ..."]
    GF_Equation --> Sum_GF
    Sum_GF --> Result["A(x) = 1 + x * A(x) * A(x) <br/> A(x) = 1 + x * A(x)²"]
    Result --> Quadratic["x A(x)² - A(x) + 1 = 0"]
    Quadratic --> Solve["Solve quadratic for A(x):<br/>A(x) = (1 ± √(1 - 4x)) / (2x)"]
    Solve --> ChooseSign["Choose negative sign for Taylor expansion at x=0 (C(0)=1):<br/>A(x) = (1 - √(1 - 4x)) / (2x)"]
    
```


---

## 5. Selected Properties of Catalan Numbers

Catalan numbers possess many interesting mathematical properties.

```mermaid
---
title: "Selected Properties of Catalan Numbers"
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
    subgraph PropertiesGraph["Key Properties"]
        P1["Oddity Condition"]
        P1_Desc["C(n) is odd if and only if n = 2<sup>k</sup> - 1 for k ≥ 0.<br/><br/>e.g., C(0)=1 (k=0), C(1)=1 (k=1), C(3)=5 (k=2), C(7)=429 (k=3)"]
        P1 --> P1_Desc

        P2["Limit of Ratio"]
        P2_Desc["lim<sub>n→∞</sub> C(n)/C(n-1) = 4"]
        P2 --> P2_Desc

        P3["Prime and Semiprime Values"]
        P3_Desc["Only prime Catalan numbers:<br/> C(2)=2, C(3)=5.<br/><br/> Only semiprime Catalan number: C(4)=14.<br/><br/>Number of prime divisors (with multiplicity) grows without limit."]
        P3 --> P3_Desc

        P4["Hankel Transform"]
        P4_Desc["The Hankel transform of C(n) gives a sequence of all 1s.<br/><br/>Det(H<sub>k</sub>) = 1, where H<sub>k</sub> is the k<sup>th</sup> Hankel matrix.<br/><br/>Example (k=3 for C(0)...C(5)):<br/>Det | 1  1  2 | = 1<br/>    | 1  2  5 |<br/>    | 2  5 14 |"]
        P4 --> P4_Desc

        P5["Convolution Property<br/>(Recursion)"]
        P5_Desc["C(n) = Σ_{k=0}^{n-1} C(k)C(n-1-k)<br/>Describes how C(n) shifts left when convolved with itself (if leading 1 is treated appropriately)."]
        P5 --> P5_Desc
        
        P6["Asymptotic Behavior"]
        P6_Desc["C(n) ≈ 4<sup>n</sup> / (n<sup>3/2</sup>√(π))"]
        P6 --> P6_Desc
    end
    
```


----

## 6. Computational Approaches for C(n)

There are several ways to compute Catalan numbers.

```mermaid
---
title: "Computational Approaches for C(n)"
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
    Compute["Compute C(n)"]
    Compute --> M1["Direct Binomial Formula:<br/>C(n) = binomial(2n, n) / (n+1)"]
    M1_Detail["Requires arbitrary-precision arithmetic for large n"]
    M1 --> M1_Detail

    Compute --> M2["Recursive Formula:<br/>C(n) = Σ_{k=0}^{n-1} C(k)C(n-1-k)<br/><br/>Base: C(0)=1"]
    M2_Detail["Can be slow due to recomputations; memoization helps"]
    M2 --> M2_Detail

    Compute --> M3["Simplified Recursion:<br/>C(n) = (2(2n-1)/(n+1)) * C(n-1)<br/><br/>Base: C(0)=1"]
    M3_Detail["Efficient iterative calculation"]
    M3 --> M3_Detail

    Compute --> M4["Generating Function Expansion:<br/>A(x) = (1 - √(1 - 4x)) / (2x)<br/><br/>Find coefficient of x<sup>n</sup>"]
    M4_Detail["Involves Taylor series expansion"]
    M4 --> M4_Detail

    Compute --> M5["Programming Language Support"]
    M5 --> M5_Maple["Maple:<br/>'binomial(2*n,n)/(n+1)' or 'combstruct'"]
    M5 --> M5_Mathematica["Mathematica:<br/> 'CatalanNumber[n]'"]
    M5 --> M5_PARI["PARI/GP:<br/>'binomial(2*n,n)/(n+1)'"]
    M5 --> M5_Python["Python:<br/>Iterative using simplified recursion or gmpy2 for large n"]
    M5 --> M5_Sage["Sage:<br/>'catalan_number(n)'"]
```

---

## 7. OEIS Entry Structure (A000108 Example)

The OEIS entry for A000108 is extensive and follows a standard structure, which is typical for many well-documented sequences.

```mermaid
---
title: "OEIS Entry Structure (A000108 Example)"
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
root(("OEIS Entry Structure for A000108"))
    ID_and_Sequence["ID and Sequence"]
      A000108
      List_of_initial_terms["List of initial terms<br/>(1, 1, 2, 5, ...)"]
    Offset
      Indicates_the_starting_index_of_the_sequence["Indicates the starting index of the sequence<br/>(e.g., 0,3)"]
    Comments
      General_information["General information, history<br/>(Segner numbers)"]
      Key_properties["Key properties"]
	      e.g., 'longest entry'
      Numerous combinatorial interpretations detailed
      Mathematical_properties["Mathematical properties"]
	      divisibility
	      primality
	      limits
	      transforms
      Connections_to_other_mathematical_areas["Connections to other mathematical areas<br/>(Schubert calculus, monoids, etc.)"]
    References
      Extensive list of academic papers, books
      Demonstrates ubiquity and research depth
    Links
      URLs to external resources, papers, interactive tools
      MathWorld, Wikipedia, personal pages of mathematicians
    Formula
      Explicit_formulas["Explicit formulas<br/>(binomial, product)"]
      Recurrence relations
      Generating_functions["Generating functions<br/>(o.g.f., e.g.f.)"]
      Asymptotic formulas
      Integral representations
      Continued fractions
    Example
      Illustrative_examples_for_specific_interpretations["Illustrative examples for specific interpretations<br/>(e.g., parenthesization for n=3)"]
      Examples of calculations or properties
    Maple
      Code snippets for Maple
    Mathematica
      Code snippets for Mathematica
    PROG["PROG<br/>(Programs)"]
      Code_snippets_for_various_other_languages["Code snippets for various other languages<br/>(PARI/GP, MuPAD, Magma, Haskell, Python, GAP, Sage, Maxima)"]
    Crossrefs
      Links_to_related_OEIS_sequences["Links to related OEIS sequences (e.g., A000984 - central binomial coefficients)"]
      Sequences that are transforms or variants
    Keyword
      Descriptive_tags["Descriptive tags (core, nonn, easy, eigen, nice, changed)"]
    Author
      Person["Person(s) who submitted/curated the entry"]
    Status
      Approval_status["Approval status (e.g., approved)"]
      
```



---

> **License and Attribution**
> - Mathematical data and exposition adapted from **The Online Encyclopedia of Integer Sequences** (<https://oeis.org/>), [OEIS sequence A000108](https://oeis.org/A000108), © OEIS Foundation Inc., licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) [![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-sa/4.0/).
> - Legal details in [LICENSE-CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0) and at [Creative Commons official site](https://creativecommons.org/licenses/by-sa/4.0/).
> - Diagram and explanatory code © 2025 Cong Le, **MIT License** [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) (for code **only**)- Full text in [LICENSE](LICENSE) file.
> - If you adapt, redistribute, or make derivative works involving *OEIS-based content*, you must retain this notice and apply **CC BY-SA 4.0**.

---

