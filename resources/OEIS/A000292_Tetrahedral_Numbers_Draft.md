---
title: "Visualizing OEIS A000292 - The Tetrahedral Numbers - Draft"
author: Cong Le
created: 2025-05-08
version: 1.0
---

> **Source Attribution:**
>
> This document incorporates or adapts material from:
> - **The Online Encyclopedia of Integer Sequences** ([https://oeis.org/](https://oeis.org/))
> - Specific sequence: [OEIS A000292](https://oeis.org/A000292)
> - © The OEIS Foundation Inc.
>
> **License:**
> 
> - **OEIS-derived content** (any mathematical data, structure, text, or visuals based on OEIS): **CC BY-SA 4.0**
> - If you adapt/redistribute these portions, you **must** provide attribution as above and license your derivative work under the same terms.
> - **Original diagram source code** (e.g., Mermaid, PlantUML, or script syntax BY CONG LE, not including OEIS math/data): **MIT License**, unless otherwise stated.
> - If you reuse just the code itself for unrelated subjects, **MIT** applies.


# Visualizing OEIS A000292 - The Tetrahedral Numbers - Draft


The following collection of **Mermaid diagrams** comprehensively illustrates the core mathematical, combinatorial, geometric, and algebraic concepts in the extensive documentation for [OEIS A000292 (Tetrahedral Numbers)](https://oeis.org/A000292).

---

## 1. Definition and Formulae

### a. Binomial and Closed Formula

```mermaid
---
title: "Binomial and Closed Formula"
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
    A["Start with n"]
    B["Tetrahedral Number a(n)"]
    A -->|Formula| B
    B --> C1["a(n) = C(n+2, 3)"]
    B --> C2["a(n) = n·(n+1)·(n+2)/6"]
    B --> C3["a(n) = Σₖ₌₀ⁿ T(k) <br/>(T(k): triangular number)"]
    C3 --> C4["T(k) = k(k+1)/2"]
    
```

### b. Generating Function

```mermaid
---
title: "Generating Function"
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
    GF["Generating Function"]
    GF -->|ordinary| OGF["G(x) = x / (1-x)^4"]
    GF -->|exponential| EGF["E(x) = (x^3/6 + x^2 + x)·exp(x)"]
    
```


---

## 2. Visual Interpretations

### a. Triangular Pyramid (“Stacking Balls”) Visualization

```mermaid
---
title: "Triangular Pyramid (“Stacking Balls”) Visualization"
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
    P1["Base layer:<br/> n balls per edge"]
    P2["2nd layer:<br/> n-1 balls per edge ..."]
    P3["Top:<br/> 1 ball"]
    P1 --> P2 --> P3
    P4["Sum layers:<br/> a(n) = total balls"]
    P3 --> P4
    
```

### b. Polyhedral Numbers Context

```mermaid
---
title: "Polyhedral Numbers Context"
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
    Polyhedra["Platonic Solid (Polyhedral) Numbers"]
    Polyhedra --> Td["Tetrahedral:<br/> a(n),<br/> A000292"]
    Polyhedra --> Cb["Cube:<br/> A000578"]
    Polyhedra --> Oh["Octahedral:<br/> A005900"]
    Polyhedra --> Dc["Dodecahedral:<br/> A006566"]
    Polyhedra --> Ic["Icosahedral:<br/> A006564"]
    Td -. is one of .-> Polyhedra
    
```

---

## 3. Combinatorial Interpretations

### a. Multinomial and Permutation Structures

```mermaid
---
title: "Multinomial and Permutation Structures"
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
flowchart TB
    Comb1["Ways to select 3 elements from n+2:<br/> C(n+2,3)"]
    Comb2["Number of nondecreasing triples from set of size n"]
    Comb3["Number of strictly increasing triples from set of size n+2"]
    Comb4["Ordered sequences of 4 nonnegative integers summing to n"]
    Comb1 -.-> Comb2
    Comb1 -.-> Comb3
    Comb4 -. "counted by" .-> Comb1
    
```

### b. Partition and Coloring

```mermaid
---
title: "Partition and Coloring"
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
    Color_Graph["Coloring a triangle's vertices with ≤n colors"]
    Color_Group["Symmetries:<br/> Rotations + Reflections<br/>(D₆, cycle index)"]
    Color_Graph --> Color_Group
    Color_Group -->|"counted as"| Color_Count["a(n) = (1/6)(n³+3n²+2n)"]
    
```

---

## 4. Algebraic, Matrix, and Recurrence Connections

### a. Linear Recurrence

```mermaid
---
title: "Linear Recurrence"
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
    R1["a(n) = 4·a(n-1) - 6·a(n-2) + 4·a(n-3) - a(n-4)"]
    R2["a(n) = a(n-2) + n² (n>1)"]
    R1 --> R2
    
```

### b. Pascal Matrix and Related Diagonals

```mermaid
---
title: "Pascal Matrix and Related Diagonals"
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
    Pas_Mat["Pascal Triangle<br/>(Binomial Coefficients)"]
    Fourth_Diag["Take diagonal k=3:<br/> C(n+2,3)"]
    Pas_Mat --> Fourth_Diag
    Fourth_Diag -->|produces| a_n["a(n)"]
    
```

### c. Matrix Determinant

```mermaid
---
title: "Matrix Determinant"
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
flowchart TB
    Det_Def["a(n) = determinant of 3x3 binomial matrix"]
    Det_Def -- explain --> Det_Mat["Rows:<br/>binomial coefficients C(n+i, j),<br/>i,j=1..3"]
    
```

---

## 5. Geometric and Graph Theoretical Links

### a. Triangular Matchsticks, Grid Circles, Polytope Vertices

```mermaid
---
title: "Triangular Matchsticks, Grid Circles, Polytope Vertices"
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
flowchart TB
    TdNum["Tetrahedral number a(n)"]
    TdNum -->|"Triangles in matchstick arrangement"| Match["Count triangles of all sizes/orientations"]
    TdNum -->|"Circles in n×n integer grid"| CircleGrid
    TdNum -->|"Vertices of certain polytopes"| PolytopeVert
    
```

### b. Wiener Index and Graphs

```mermaid
---
title: "Wiener Index and Graphs"
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
    PathGraph["Path graph with n+1 vertices"]
    WienerIndex["Wiener index = a(n)"]
    PathGraph --> WienerIndex
    MaxWien["Maximum Wiener index for graphs with n+1 vertices"]
    WienerIndex -.-> MaxWien
    
```

---

## 6. Relations to Related Sequences (OEIS Crosslinks)

```mermaid
---
title: "Relations to Related Sequences (OEIS Crosslinks)"
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
    Td["a(n):<br/> Tetrahedral Numbers<br/>(A000292)"]
    SqPyra["Square pyramidal<br/>(A000330)"]
    Triangle["T(n):<br/> Triangular Numbers<br/>(A000217)"]
    Cube["Cubes<br/>(A000578)"]
    Octa["Octahedral Numbers<br/>(A005900)"]
    Dodec["Dodecahedral Numbers<br/>(A006566)"]
    Icosa["Icosahedral Numbers<br/>(A006564)"]
    Td -- "partial sums" --> A000332["A000332"]
    Td -- "relations via binomial identities" --> Triangle
    Td -- "arithmetic mean with A000330" --> SqPyra
    Td -- "base for cube decomposition" --> Cube
    Td --> Octa
    Td --> Dodec
    Td --> Icosa
    
```

---

## 7. Computational and Algorithmic Aspects

### a. Common Code / Generating Program Map

```mermaid
---
title: "Common Code / Generating Program Map"
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
    InputN["Input n"]
    Calc1["Compute a(n) = n(n+1)(n+2)/6"]
    Calc2["Or:<br/> a(n) = binomial(n+2,3)"]
    Output["Return a(n)"]
    InputN --> Calc1 --> Output
    InputN --> Calc2 --> Output
    
```

---

## 8. Symmetry, Recurrence, and "Matryoshka" Patterns

### a. Matryoshka/Folded Structure

```mermaid
---
title: "Matryoshka/Folded Structure"
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
    TetrahedralSeq["A000292<br/>(n*(n+1)*(n+2)/6)"]
    PartialSum["Partial sum:<br/> leads to A000332 (binomial(n+4,4)/24)"]
    Rec["Recurrence:<br/> a(n) = a(n-2) + n^2"]
    TetrahedralSeq --> PartialSum
    TetrahedralSeq <--> Rec
    TetrahedralSeq -. "Odd/even bisection<br/>relates to odd/even squares" .-> OddEven
    
```

---

## 9. Applications and Appearances

```mermaid
---
title: "Applications and Appearances"
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
flowchart TB
    Appl1["Balls in triangular pyramid"]
    Appl2["Gifts up to n-th day in 'Twelve Days of Christmas'"]
    Appl3["Valid colorings in geometry/group theory"]
    Appl4["Number theory:<br/> Diophantine equations"]
    Appl5["Graph Science:<br/> Graphs, permutations, indices"]
    Appl6["Physics:<br/> Quantum, String theory, Tensor components"]

    Appl1 -->|"a(n) interpretation"| Td
    Appl2 -->|"a(n)"| Td
    Appl3 -->|"various colorings and symmetries"| Td
    Appl4 -->|"solutions"| Td
    Appl5 -->|"e.g. cycles, Wiener index"| Td
    Appl6 -->|"e.g. commutator, spin"| Td
    
```

---

## 10. Summary Table: Central Identities and Properties - TODO 

```mermaid
classDiagram
    class TetrahedralNumber {
        + a(n) = binomial(n+2, 3)
        + a(n) = n(n+1)(n+2)/6
        + G.f.: x / (1-x)^4
        + E.g.f.: (x³/6 + x² + x)·eˣ
        + Recurrence: a(n) = 4a(n-1) - 6a(n-2) + 4a(n-3) - a(n-4)
        + Partial sum: Σₖ₌₀ⁿ T(k)
        + Antidiagonal sum: in multiplication table
        + Matrix det: see documentation
        + a(n) = sum_{k=1}^n sum_{j=0}^k j
        + a(n) ~ n³/6 (asymptotic)
    }
```

---

## 11. Interlinked Structures, Themes, and Cross-Domain Connections

```mermaid
---
title: "Interlinked Structures, Themes, and Cross-Domain Connections"
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
flowchart TB
    Tetrahedral["Tetrahedral Number"]
    Combinatorial[["Combinatorics:<br/>selection, coloring, partition"]]
    Algebraic[["Algebra:<br/>Binomial, Matrix, Recurrence"]]
    Geometric[["Geometry:<br/>Polyhedra, Grids, Matchsticks, Polytopes"]]
    GraphTheory[["Graph Theory:<br/>Vertices, Index, Cycles"]]
    Physics[["Physics:<br/>Tensor, String Theory, Spin"]]
    Applications[("Applications:<br/>Music, Gifts, Algorithms")]
    Tetrahedral -- "Central object linking all domains" --- Combinatorial
    Tetrahedral --- Algebraic
    Tetrahedral --- Geometric
    Tetrahedral --- GraphTheory
    Tetrahedral --- Physics
    Tetrahedral --- Applications
    
    classDef cluster fill:#fee,stroke:#f77
    
```

---

## 12. Growth Pattern and Sequence Visualization

### a. Initial Values Chart (Compact)

```mermaid
---
title: "Initial Values Chart (Compact)"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  theme: default
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%%%%%%% Toggle theme value to `base` to activate the initilization below for the customized theme version.
%%{
  init: {
    'pie': { 'htmlLabels': false },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#B528',
      'fontSize': '15px'
    }
  }
}%%
pie showData
    title Tetrahedral numbers (first 10 terms)
    "0": 0
    "1": 1
    "2": 4
    "3": 10
    "4": 20
    "5": 35
    "6": 56
    "7": 84
    "8": 120
    "9": 165
```

---

## 13. Primary Cross-References Navigable Map

```mermaid
---
title: "Primary Cross-References Navigable Map"
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
    TetraA000292["A000292<br>Tetrahedral"]
    TriangleA000217["A000217<br>Triangular numbers"]
    SqPyramidA000330["A000330<br>Square pyramidal"]
    DodecA006566["A006566<br>Dodecahedral"]
    OctaA005900["A005900<br>Octahedral"]
    IcosaA006564["A006564<br>Icosahedral"]
    CubeA000578["A000578<br>Cubes"]

    TetraA000292 -->|Partial sum| SqPyramidA000330
    TetraA000292 --- DodecA006566
    TetraA000292 --- OctaA005900
    TetraA000292 --- IcosaA006564
    TetraA000292 --- CubeA000578
    TriangleA000217 --"triangular foundation"--> TetraA000292
```

---

## 14. Antidiagonal in Multiplication Table Illustration

```mermaid
---
title: "Antidiagonal in Multiplication Table Illustration"
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
    MT["Multiplication Table"]
    MT --> ATI["Antidiagonal Sums = a(n)"]
    ATI --> Value["Sum of numbers where i + j = n+2"]
    
```

---

## 15. Symmetries and Colorings in Triangles

```mermaid
---
title: "Symmetries and Colorings in Triangles"
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
    TriangleVertices["Triangle Vertices:<br/> 3"]
    ColorChoices["≤ n colors"]
    SymmGroup["Dihedral Group D₆:<br/> Rotations & Reflections"]
    Z["Cycle Index:<br/> (x₁³ + 2x₃ + 3x₁x₂)/6"]
    
    TriangleVertices --> ColorChoices --> SymmGroup --> Z
    
    Z -->|"counts up to symmetry"| ColorCount["a(n)"]
    
```


---

**License and Attribution**

> - Mathematical data and exposition adapted from **The Online Encyclopedia of Integer Sequences** (<https://oeis.org/>), [OEIS sequence A000292](https://oeis.org/A000292), © OEIS Foundation Inc., licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) [![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-sa/4.0/).
> - Legal details in [LICENSE-CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0) and at [Creative Commons official site](https://creativecommons.org/licenses/by-sa/4.0/).
> - Diagram and explanatory code © 2025 Cong Le, **MIT License** [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) (for code **only**)- Full text in [LICENSE](LICENSE) file.  
>  
> - If you adapt, redistribute, or make derivative works involving *OEIS-based content*, you must retain this notice and apply **CC BY-SA 4.0**.

---

