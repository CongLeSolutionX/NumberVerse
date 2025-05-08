---
created: 2025-05-07 05:31:26
author: Cong Le
version: "1.0"
license(s): MIT, CC BY 4.0
copyright: Copyright (c) 2025 Cong Le. All Rights Reserved.
source: https://oeis.org/A000045
---



# Fibonacci Sequence (A000045) - A Diagrammatic Guide 
> **Disclaimer:**
>
> This document contains my personal notes on the topic,
> compiled from publicly available documentation and various cited sources.
> The materials are intended for educational purposes, personal study, and reference.
> The content is dual-licensed:
> 1. **MIT License:** Applies to all code implementations (Swift, Mermaid, and other programming languages).
> 2. **Creative Commons Attribution 4.0 International License (CC BY 4.0):** Applies to all non-code content, including text, explanations, diagrams, and illustrations.
---

## 1. Fibonacci Sequence: Core Definition and History

This diagram provides a basic introduction, the recurrence relation, initial terms, and a simplified historical timeline.

```mermaid
---
title: "Fibonacci Sequence: Core Definition and History"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
flowchart TD
    subgraph OEIS_A000045["OEIS A000045"]
        ID["OEIS A000045:<br/>Fibonacci Numbers"]
        Def["F(n) = F(n-1) + F(n-2)"]
        Initial["F(0) = 0, F(1) = 1"]
        Seq["Sequence:<br/> 0, 1, 1, 2, 3, 5, 8, 13, ..."]
        ID --> Def --> Initial --> Seq
    end

    subgraph Historical_Context["Historical Context"]
    direction LR
        Pingala["Pingala (c. 200 BC, India)<br/>Rhythmic Patterns"] --> Virahanka["Virahanka<br/>(c. 700 AD, India)"]
        Virahanka --> Gopala["Gopala<br/>(c. 1135 AD, India)"]
        Gopala --> Hemachandra["Hemachandra<br/>(c. 1150 AD, India)<br/>Explicit mention:<br/> 1,2,3,5,8..."]
        Hemachandra --> Fibonacci["Fibonacci<br/>(Leonardo of Pisa, c. 1202 AD, Italy)<br/>Liber Abaci, Rabbit Problem"]
        
    end

    Seq --> Historical_Context
    Historical_Context -.-> Note1
    Note1["Note:<br/>Known in India long before Fibonacci"]

    Seq --> AltNames["Alternative Names"]
    AltNames --> HemachandraNumbers["Hemachandra Numbers"]
    AltNames --> LameSequence["Lamé's Sequence"]
    AltNames --> GopalaHema["Gopala-Hemachandra Numbers<br/>(generalized)"]

    style ID fill:#f9f,stroke:#333,stroke-width:2px
    style Def fill:#lightgrey,stroke:#333
    style Initial fill:#lightgrey,stroke:#333
    style Seq fill:#ccf,stroke:#333,stroke-width:2px
    style Historical_Context fill:#f2d2,stroke:#333,stroke-width:1px
    
```


---

## 2. Key Mathematical Formulas for F(n)

This diagram highlights some of the fundamental explicit and approximate formulas for calculating Fibonacci numbers.

```mermaid
---
title: "Key Mathematical Formulas for F(n)"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
flowchart TD
    subgraph Formulas["Key Formulas for F(n)"]
    direction LR
        F1["Recurrence Relation:<br/>F(n) = F(n-1) + F(n-2)<br/>F(0)=0, F(1)=1"]

        F2["Binet's Formula:<br/>F(n) = (φⁿ - ψⁿ) / √5<br/><br/>φ = (1+√5)/2<br/>(Golden Ratio)<br/><br/>ψ = (1-√5)/2"]

        F3["Approximation:<br/>F(n) = round(φⁿ / √5)<br/>For n ≥ 0"]

        F4["Matrix Form:<br/>  [ F(n+1)  F(n)   ]<br/>  [ F(n)    F(n-1) ] = <br/> [ 1  1 ]ⁿ<br/>  [ 1  0 ]"]
        
        Note_Matrix["Alternative Matrix Form:<br/>[0 1; 1 1]^n * [0; 1] = [F(n); F(n+1)]"]
        
        F4 --> Note_Matrix

        F5["Ordinary Generating Function<br/>(O.G.F.):<br/><br/>G(x) = Σ F(n)xⁿ <br/>= x / (1 - x - x²)"]

        F6["Exponential Generating Function<br/>(E.G.F.):<br/>E(x) = Σ F(n)xⁿ/n! = (e^(φx) - e^(ψx)) / √5<br/>= (2/√5) * e^(x/2) * sinh(x√5/2)"]

    end

    style Formulas fill:#fa2d,stroke:#333,stroke-width:2px
    style F1 fill:#eef2
    style F2 fill:#eef2
    style F3 fill:#eef2
    style F4 fill:#eef2
    style F5 fill:#eef2
    style F6 fill:#eef2

```

---

## 3. Sampler of Combinatorial Interpretations

Fibonacci numbers appear in a vast array of counting problems. This diagram shows a few common examples.

```mermaid
---
title: "Sampler of Combinatorial Interpretations"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
    Root["Fibonacci Numbers Count..."] --> C1
    
    subgraph C1["F(n+2):<br/>Binary Sequences"]
    direction TB
        C1_Desc["Number of binary sequences of length n<br/>that have no consecutive 0's"]
        C1_Ex["n=3 (F(5)=5):<br/>111, 011, 101, 110, 010"]
    end

    Root --> C2
    subgraph C2["F(n+2):<br/>Subsets with No Consecutive Integers"]
    direction TB
        C2_Desc["Number of subsets of {1, 2, ..., n}<br/>that contain no consecutive integers"]
        C2_Ex["n=3 (F(5)=5):<br/>{}, {1}, {2}, {3}, {1,3}"]
    end

    Root --> C3
    subgraph C3["F(n+1):<br/> Domino Tilings"]
    direction TB
        C3_Desc["Number of ways to tile a 2 x n rectangle<br/>with 2 x 1 dominoes"]
        C3_Ex["n=3 (F(4)=3):<br/>III (all vertical)<br/>=II (1 horiz pair, 1 vert)<br/>II= (1 vert, 1 horiz pair)"]
        C3_Vis["Visually:<br/>[V V V]<br/>[H V]<br/>[V H]<br/>(H = horizontal pair)"]
         C3_Ex --> C3_Vis
    end

    Root --> C4
    subgraph C4 ["F(n):<br/>Compositions"]
    direction TB
        C4_DescA["F(n) = Number of compositions of n-1<br/>with no part greater than 2.<br/>(i.e., parts are only 1s and 2s)"]
        C4_ExA["n=4, F(4)=3, compositions of 3:<br/>1+1+1, 1+2, 2+1"]
        C4_DescB["F(n) = Number of compositions of n<br/>into odd parts"]
        C4_ExB["n=4, F(4)=3, compositions of 4:<br/>1+1+1+1, 1+3, 3+1"]
    end

    Root --> C5
    subgraph C5["F(n):<br/>Pascal's Triangle Diagonals"]
    direction TB
        C5_Desc["F(n) is the sum of entries on a 'shallow' diagonal<br/>in Pascal's triangle"]
        C5_Vis["Pascal's Triangle Snippet:<br/>      1<br/>     1 1<br/>    1 2 1<br/>   1 3 3 1<br/>  1 4 6 4 1<br/>F(1)=1 (1)<br/>F(2)=1 (1)<br/>F(3)=2 (1+1)<br/>F(4)=3 (1+2)<br/>F(5)=5 (1+3+1)<br/>_Sums along (binomial(n-k,k))_"]
    end

    style Root fill:#c22,stroke:#333,stroke-width:2px
    style C1 fill:#d4f8e8
    style C2 fill:#d4f8e8
    style C3 fill:#d4f8e8
    style C4 fill:#d4f8e8
    style C5 fill:#d4f8e8
    
```


---


## 4. Relationship with Golden Ratio (φ) and Lucas Numbers (L(n))

Fibonacci numbers are deeply intertwined with the Golden Ratio and Lucas numbers.

```mermaid
---
title: "Relationship with Golden Ratio (φ) and Lucas Numbers (L(n))"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
    subgraph Core_Entities["Core Entities"]
        FN["F(n)<br/>Fibonacci Numbers"]
        PHI["φ<br/>(Golden Ratio)<br/>(1 + √5) / 2 <br/>≈ 1.618"]
        LN["L(n)<br/>Lucas Numbers<br/>L(n)=L(n-1)+L(n-2)<br/>L(0)=2, L(1)=1<br/><br/>(2,1,3,4,7,11,...)"]
    end

    subgraph Relationships["Relationships"]
        R1["Limit F(n+1)/F(n) → φ as n → ∞"]
        R2["φⁿ = F(n)φ + F(n-1)"]
        R3["L(n) = F(n-1) + F(n+1)"]
        R4["Cassini's Identity related:<br/>L(n)² - 5F(n)² = 4(-1)ⁿ"]
        R5["Binet's Formula uses φ:<br/>F(n) = (φⁿ - (1-φ)ⁿ) / √5"]
        R6["F(2n) = F(n)L(n)"]
    end

    FN --> R1
    PHI --> R1
    FN --> R2
    PHI --> R2
    FN --> R3
    LN --> R3
    FN --> R4
    LN --> R4
    FN --> R5
    PHI --> R5
    FN --> R6
    LN --> R6


    style FN fill:#ccf2,stroke:#333,stroke-width:2px
    style PHI fill:#fd70,stroke:#333,stroke-width:2px
    style LN fill:#9e90,stroke:#333,stroke-width:2px
    style Relationships fill:#f8f2,stroke:#ccc
    
```

---


## 5. Key Algebraic Identities

This diagram illustrates some famous identities involving Fibonacci numbers.

```mermaid
---
title: "Key Algebraic Identities"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
    Title["Key Fibonacci Algebraic Identities"]

    subgraph Idents["Idents"]
        I1["**Cassini's Identity (Simson's Formula):**<br/>F(n-1)F(n+1) - F(n)² = (-1)ⁿ"]
        I2["**d'Ocagne's Identity:**<br/>F(m)F(n+1) - F(m+1)F(n) = (-1)ⁿF(m-n)"]
        I2_Variant["_Variant used in doc to prove Rashid's conjecture:_ <br/>F(n)F(m) + F(n+1)F(m+1) = F(n+m+1)"]
        I3["**Sum of first n Fibonacci numbers:**<br/>Σ_{k=0 to n} F(k) = F(n+2) - 1"]
        I4["**Sum of squares:**<br/>Σ_{k=0 to n} F(k)² = F(n)F(n+1)"]
        I5["**Honsberger's Identity (related to F(n+m)):**<br/>F(n+m) = F(n-1)F(m) + F(n)F(m+1)"]
    end

    Title --> Idents

    style Title fill:#c22,stroke:#333,stroke-width:2px
    style Idents fill:#f0fff0,stroke:#ccc
    style I1 fill:#e0ffff
    style I2 fill:#e0ffff
    style I3 fill:#e0ffff
    style I4 fill:#e0ffff
    style I5 fill:#e0ffff
    
```

---

## 6. Divisibility Properties

Fibonacci numbers exhibit interesting divisibility patterns.

```mermaid
---
title: "Divisibility Properties"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
    Title["Fibonacci Divisibility Properties"]

    P1["**Basic Recurrence:**<br/>F(n) = F(n-1) + F(n-2)"]

    P2["**F(n) divides F(m) if n divides m** <br/>(for n > 0)"]
    P2_Ex["Example:<br/> F(3)=2, F(6)=8.<br/> 2 divides 8.<br/> 3 divides 6."]

    P3["**Strong Divisibility Sequence:**<br/>gcd(F(n), F(m)) = F(gcd(n, m))"]
    P3_Ex["Example:<br/> gcd(F(6), F(9)) = gcd(8, 34) = 2<br/>F(gcd(6,9)) = F(3) = 2"]

    P4["**Pisano Periods (A001175):**<br/>The sequence F(n) mod m is periodic.<br/>The length of this period is called the Pisano period π(m)."]
    P4_Ex["F(n) mod 3: 0,1,1,2,0,2,2,1, <br/>(0,1,1,2,0,2,2,1,...) <br/>Period π(3)=8"]

    P5["**Entry Points (A001177):**<br/>For a prime p, the smallest k > 0 such that F(k) ≡ 0 (mod p) is the entry point of p."]
    P5_Rel["Related to divisibility by p:<br/><br/>- p | F(p-1) if p ≡ ±1<br/>(mod 5)<br/><br/>- p | F(p+1) if p ≡ ±2<br/>(mod 5)<br/><br/>- F(5) = 5, so 5 | F(5)"]

    Title --> P1
    P1 --> P2 --> P3
    P1 --> P4
    P1 --> P5
    P2 --> P2_Ex
    P3 --> P3_Ex
    P4 --> P4_Ex
    P5 --> P5_Rel

    style Title fill:#f6c1,stroke:#333,stroke-width:2px
    style P2 fill:#eeb6
    style P3 fill:#eeb6
    style P4 fill:#eeb6
    style P5 fill:#eeb6
    
```


---

## 7. Generating Function Interconnections (Inspired by Tom Copeland's Comment)

This diagram outlines how the ordinary generating function (o.g.f.) for Fibonacci numbers can be related to o.g.f.s of other important sequences like Catalan, Fine, and Motzkin numbers, through functional composition.

```mermaid
---
title: "Generating Function Interconnections (Inspired by Tom Copeland's Comment)"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
    subgraph BaseFunctions["Base Building Blocks"]
        PX["P(x) = x / (1+x)"]
        PINVX["P⁻¹(x) = x / (1-x)"]
        CX["C(x) = (1 - √(1-4x)) / 2<br/>(o.g.f. for shifted Catalan A000108)"]
        CINVX["C⁻¹(x) = x(1-x)"]
        PX --- PINVX
        CX --- CINVX
    end

    subgraph DerivedOGFs["Derived O.G.F.s"]
        FINX["Fin(x) = P(C(x))<br/>(o.g.f. for Fine numbers A000957)"]
        MOTX["Mot(x) = C(P(x))<br/>(o.g.f. for shifted Motzkin/Riordan A005043)"]
        BTCX["BTC(x) = C(P⁻¹(x))<br/>(o.g.f. for Binomial Transform of Catalan A007317)"]

        PX --"compose"--> FINX
        CX --"compose"--> FINX

        CX --"compose"--> MOTX
        PX --"compose"--> MOTX

        CX --"compose"--> BTCX
        PINVX --"compose"--> BTCX
    end

    subgraph FibonacciOGF["Fibonacci O.G.F. Relation"]
        FIBX_raw["F_shifted(x) = (x+x²)/(1-x-x²)<br/>(o.g.f. for F(n+1) starting F(1)=1, F(2)=1, F(3)=2, ...)"]
        FIBX_relation["F_shifted(x) = -P(C⁻¹(-x))"]
        FIBX_note["Note:<br/> Document uses x/(1-x-x²) for F(0)=0, F(1)=1,..."]
        PINVX --"input -x"--> NegPINVX["-P⁻¹(-x) = P(x)"]
        CINVX --"input -x"--> NegCINVX["C⁻¹(-x) = -x(1+x)"]
        NegPINVX --"compose"--> Step1["-C(P⁻¹(-x)) = -BTC(-x)"]
        Step1 --"This equals Inverse of Fib_shifted(x)"--> FibInv["Fib_shifted⁻¹(x) = -BTC(-x)"]
        FibInv --> FIBX_raw
        FIBX_raw -.-> FIBX_relation
        FIBX_raw -.-> FIBX_note

        Comment["Tom Copeland's comment shows complex relations.<br/>Original sequence F(n) (0,1,1,2,...) has o.g.f. x/(1-x-x²).<br/>If F_raw(x) = x/(1-x-x²), then F_raw(x) = x * Sum F(n+1)x^n for n>=0"]
    end


    style BaseFunctions fill:#E0FFFF, stroke:#333
    style DerivedOGFs fill:#FFFACD, stroke:#333
    style FibonacciOGF fill:#F0FFF0, stroke:#333
    
```

*Note: The Copeland's comment is quite dense. This diagram attempts to show the composition idea. The definition of "shifted" Fibonacci `FIBX_raw` here aims to match the structure that -P(Cinv(-x)) would yield, which starts with x. The standard F(n) g.f. `x/(1-x-x^2)` is F(0)x^0 + F(1)x^1 + F(2)x^2 ... = 0 + x + x^2 + 2x^3 + ...*

---

## 8. Python Generator for Fibonacci Sequence

Illustrating the logic of the provided Python code snippet `fib_gen`.

```mermaid
---
title: "Python Generator for Fibonacci Sequence"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
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
    Start["Start fib_gen()"] --> Init["Initialize x=0, y=1"]
    Loop["Infinite Loop<br/>(while True)"] --> Yield["yield x<br/>(current Fibonacci number)"]
    Yield --> Update["Update:<br/>old_x = x<br/>x = y<br/>y = old_x + y"]
    Update --> Loop

    style Start fill:#9e9,stroke:#333,stroke-width:2px
    style Init fill:#a8e6
    style Loop fill:#f07a
    style Yield fill:#ff92
    style Update fill:#f6c1
    
```


---
**Licenses:**

- **MIT License:**  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) - Full text in [LICENSE](LICENSE) file.
- **Creative Commons Attribution 4.0 International:** [![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](LICENSE-CC-BY) - Legal details in [LICENSE-CC-BY](LICENSE-CC-BY) and at [Creative Commons official site](http://creativecommons.org/licenses/by/4.0/).

---