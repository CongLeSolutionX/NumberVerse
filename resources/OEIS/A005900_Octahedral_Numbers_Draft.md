---
title: "Visualizing OEIS A005900 - Octahedral Numbers - Darft"
author: Cong Le
created: 2025-05-08
version: 1.0
---

# Visualizing OEIS A005900 - Octahedral Numbers - Draft
> **Source Attribution:**
>
> This document incorporates or adapts material from:
> - **The Online Encyclopedia of Integer Sequences** ([https://oeis.org/](https://oeis.org/))
> - Specific sequence: [OEIS A005900](https://oeis.org/A005900)
> - **© The OEIS Foundation Inc.**
>
> **License:**
> 
> - **OEIS-derived content** (any mathematical data, structure, text, or visuals based on OEIS): **CC BY-SA 4.0**
> - If you adapt/redistribute these portions, you **must** provide attribution as above and license your derivative work under the same terms.
> - **Original diagram source code** (e.g., Mermaid, PlantUML, or script syntax BY CONG LE, not including OEIS math/data): **MIT License**, unless otherwise stated.
> - If you reuse just the code itself for unrelated subjects, **MIT** applies.

---

Below is a comprehensive set of Mermaid diagrams and and explanatory illustrations capturing the structure and complexity of A005900 (the octahedral numbers sequence) from [the OEIS](https://oeis.org/A005900), describing its formulas, geometric significance, combinatorial interpretations, recurrence relations, links to polyhedral numbers, and numerous mathematical properties.

---

## 1. What is OEIS A005900?

```mermaid
---
title: "What is OEIS A005900"
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
      'primaryTextColor': '#22B',
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
root(("Octahedral Numbers<br/>OEIS A005900"))
	Definition["Definition:<br/>The sequence of octahedral numbers counts integer points in octahedra of increasing sizes:<br/>0, 1, 6, 19, 44, 85, 146, ..."]
	Sequence_ID["Sequence ID:<br/>A005900"]
	Name["Name:<br/>Octahedral numbers"]
	Formula["Formula:<br/>a(n) = n*(2n^2 + 1)/3"]
	Polyhedral_sequence["Polyhedral sequence<br/>(Platonic solids)"]
	Geometric_object["Geometric object:<br/>Octahedron"]
  
```
---

## 2. Sequence Structure & Core Formula

```mermaid
---
title: "Sequence Structure & Core Formula"
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
    A((n)) -.->|0| B0[0]
    A -.->|1| B1[1]
    A -.->|2| B2[6]
    A -.->|3| B3[19]
    A -.->|4| B4[44]
    A -.->|5| B5[85]
    A -.->|...| BX[...]
    A -.->|n| BN["a(n) = n · (2 n² + 1)/3"]
    
```

- **Offset:** `0,3` (Sequence starts at n=0; g.f. series offset)
- **General Term:**  a(n) = n·(2 n² + 1)/3

---

## 3. Defining Formulas and Equivalent Expressions

```mermaid
---
title: "Defining Formulas and Equivalent Expressions"
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
    AN["a(n)"] --> B1["a(n) = n · (2n² + 1)/3"]
    AN --> B2["a(n) = 1² + 2² + ... + n² + (n-1)² + ... + 1²"]
    AN --> B3["a(n) = 4·C(n,3) + 4·C(n,2) + C(n,1)"]
    AN --> B4["a(n) = C(n+2,3) + 2·C(n+1,3) + C(n,3)"]
    AN --> B5["a(n) = (2n^3+n)/3 = -a(-n)"]
    AN --> B6["a(n) = ((n+1)^5 - n^5 - (n^5 - (n-1)^5))/30"]
    AN --> B7["a(n) = Cube(n) - 2·Tetrahedral(n-1)"]
    AN --> B8["Generating function:<br/> g.f. = x(1 + x)²/(1 - x)^4"]
    AN --> B9["Recurrence:<br/> a(n) = 4·a(n-1) - 6·a(n-2) + 4·a(n-3) - a(n-4)"]
    AN --> B10["Exponential g.f.:<br/> (1/3)x(3 + 6x + 2x²)·e^x"]
    
```

*Legend*:  
- `C(n,k)` = binomial coefficient  
- Cube(n) = n³  
- Tetrahedral(n-1) = (n-1)(n)(n+1)/6

---

## 4. Polyhedral Relationships & Geometry

### 4.1. Platonic Solid Numbers

```mermaid
---
title: "Platonic Solid Numbers"
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
    S("Platonic Solids") --> T["Tetrahedral<br/>(A000292)"]
    S --> C["Cube<br/>(A000578)"]
    S --> O["Octahedral<br/>(A005900)"]
    S --> D["Dodecahedral<br/>(A006566)"]
    S --> I["Icosahedral<br/>(A006564)"]
    O ---|"Schläfli symbol"| Symbol["{3,4}"]
    O ---|"Vertex structure"| Vertex["5"]
    
```

### 4.2. Geometry: Octahedral Layers

```mermaid
---
title: "Geometry - Octahedral Layers"
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
    H["Octahedron of size n"]
    H --> U1["Composed of unit octahedra:<br/> a(n)"]
    H --> U2["Composed of unit tetrahedra:<br/> 8·Tetrahedral(n-1)"]
    H --> H2["Tetrahedron of size n<br/>(honeycomb)"]
    H2 --> U3["Unit tetrahedra:<br/>(n³+2n)/3"]
    H2 --> U4["Unit octahedra:<br/>(n³-n)/6"]
    
```

---

## 5. Combinatorial and Algebraic Interpretations

```mermaid
---
title: "Combinatorial and Algebraic Interpretations"
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
    A["a(n)"] --> B["Sum of products pq where p, q are positive odd and p+q=2n"]
    A --> C["Number of 5-subsets intersecting both given disjoint 2-subsets in an n-set<br/>(a(n-4))"]
    A --> D["Self-convolution of the odd numbers<br/>(A005408)"]
    A --> E["Largest coefficient of<br/>(1 + ... + x^{n-1})^4"]
    A --> F["Number of join-irreducible elements in Weyl group of type B_n, strong Bruhat order"]
    A --> G["Number of semistandard Young tableaux for partitions of 3, max element ≤ n"]
    A --> H["Partial sums of centered square numbers<br/>(A001844)"]
    A --> I["Third partial sum of<br/>(0,1,3,4,4,4,...)"]
    A --> J["Convolution square root:<br/>Odd numbers<br/>(A005408)"]
    
```

---

## 6. Recurrence and Generating Function - TODO

### 6.1. Recurrence

```mermaid
---
title: "Recurrence"
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
    'stateDiagram-v2': { 'htmlLabels': true, 'curve': 'linear' },
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
stateDiagram-v2
    [*] --> S0: a(0) = 0
    S0 --> S1: a(1) = 1
    S1 --> S2: a(2) = 6
    S2 --> S3: a(3) = 19
    S3 --> S4: a(4) = 44
    
	state S5 {
		Decription_of_state_S5: a(n) = 4·a(n-1) - 6·a(n-2) + 4·a(n-3) - a(n-4)
	}
    
    S4 --> S5
    S5 --> S5
```

### 6.2. Generating Functions

```mermaid
---
title: "Generating Functions"
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
    GF["Generating Functions"] --> GFS["Ordinary:<br/> G(x) = x(1 + x)^2 / (1 - x)^4"]
    GF --> GFE["Exponential:<br/> (1/3) x (3 + 6x + 2x^2) exp(x)"]
    
```

---

## 7. Algebraic & Programmatic Construction

```mermaid
---
title: "Algebraic & Programmatic Construction"
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
    FN(["Formulas"]) -->|"direct"| F1["a(n) = n*(2n^2 + 1)/3"]
    FN -->|"binomial"| F2["4C(n,3) + 4C(n,2) + C(n,1)"]
    FN -->|"programming"| F3["Python:<br/> def a(n):<br/>return n*(2*n*n + 1)//3"]
    FN --> F4["Maple, Mathematica, Haskell, Maxima, Magma<br/>(see PROG section)"]
    
```

---

## 8. Inter-Sequence Links (Cross-References)

```mermaid
---
title: "Inter-Sequence Links (Cross-References)"
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
    'erDiagram': { 'htmlLabels': true, 'curve': 'linear' },
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
    "A005900" ||--o{ "A000292": "Uses Tetrahedral numbers" 
    "A005900" ||--o{ "A000578": "Uses Cubes"
    "A005900" ||--o{ "A006566": "Relation to Dodecahedral numbers"
    "A005900" ||--o{ "A006564": "Relation to Icosahedral numbers"
    "A005900" ||--o{ "A005408": "Convolution & Odd numbers"
    "A005900" ||--o{ "A001844": "Partial Sums"
    "A005900" ||--o{ "A002061": "Central polygonal"
    "A005900" ||--o{ "A081277": "Chebyshev triangle"
    
```


---

## 9. Summary: Application Contexts

```mermaid
---
title: "Application Contexts Summary"
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
    'journey': { 'htmlLabels': true},
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
journey
    title Octahedral Number Sequence: Diverse Contexts
    section Geometry
      Polyhedral Numbers : 5
      Platonic Solid Classification : 4
      Unit Octahedra / Tetrahedra Count : 4
      Schläfli Symbol {3,4} : 3
    
    section Combinatorics
      Subset intersection counts : 4
      Young tableaux counts : 3
      Convolution with odd numbers : 3
    
    section Algebra
      Generating Functions, Recurrence : 4
      Chebyshev & Binomial transforms : 3
    
    section Number Theory
      Divisor lattice widths : 2
      Cube - Tetrahedral connection : 3
      Sum of products p,q (odd) : 2
    
    section Physics/Applied
      Shells of atoms (cluster chemistry) : 2
      Contact number for sphere packings : 3
      
```


---

## 10. Relationships in the Polyhedral Number Family

```mermaid
---
title: "Relationships in the Polyhedral Number Family"
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
    P["Polyhedral Number Family"]
    P --> Tetrahedral["Tetrahedral<br/>A000292"]
    P --> Cubic["Cubic<br/>A000578"]
    P --> Octahedral["Octahedral<br/>A005900"]
    P --> Dodecahedral["Dodecahedral<br/>A006566"]
    P --> Icosahedral["Icosahedral<br/>A006564"]
    
    Octahedral -->|"layered count"| OddNumbers["Odd Numbers<br/>A005408"]
    Octahedral -->|"partial sums"| CenteredSquares["Centered Squares<br/>A001844"]
    Octahedral -->|"formula link"| Tetrahedral
    Octahedral -->|"formula link"| Cubic
    
```

---

## 11. OEIS Document Structure Illustration

```mermaid
---
title: "OEIS Document Structure Illustration"
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
    R1[Comments]
    R2[References]
    R3[Links]
    R4[Formulas]
    R5[Examples]
    R6[Programs]
    R7[Crossrefs]
    R8[Keywords/Meta]
    R9[Authors/Status]
    DOC("OEIS Entry:<br/>A005900")
    DOC --> R1
    DOC --> R2
    DOC --> R3
    DOC --> R4
    DOC --> R5
    DOC --> R6
    DOC --> R7
    DOC --> R8
    DOC --> R9
    
```

---

## 12. Example Calculation Tree

Example: a(4) = 44

```mermaid
---
title: "Example Calculation Tree"
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
    N["n=4"] --> F1["a(4) = 4 · (2·4² + 1)/3 = 4 · (2·16 + 1)/3"]
    F1 --> F2["= 4 · (32 + 1)/3 = 4 · 33/3"]
    F2 --> F3["= 4 · 11 = 44"]
    N --> S1["Sum pq with p+q=8,<br/>p,q odd,<br/>p,q>0"]
    S1 --> S2["p,q=(1,7),(3,5),(5,3),(7,1)"]
    S2 --> S3["Products:<br/> 1×7, 3×5, 5×3, 7×1"]
    S3 --> S4["Sum:<br/> 7 + 15 + 15 + 7 = 44"]
    
```
 

---

## 13. Sequence Recurrence Expansion (Order 4 rec.)

```mermaid
---
title: "Sequence Recurrence Expansion (Order 4 rec.)"
author: "Cong Le"
version: "0.1"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  layout: elk
  theme: base
---
%%%%%%%% Mermaid version v11.4.1-b.14
%%{
  init: {
    'sequence': { 'mirrorActors': true, 'showSequenceNumbers': true },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#2BB8',
      'primaryBorderColor': '#7C0000',
      'lineColor': '#F8B229',
      'secondaryColor': '#6122',
      'tertiaryColor': '#fff',
      'fontSize': '15px',
      'textColor': '#F8B229',
      'actorTextColor': '#E2E',
      'fontSize': '25px',
      'stroke':'#033',
      'stroke-width': '0.2px'
    }
  }
}%%
sequenceDiagram
  participant n-4
  participant n-3
  participant n-2
  participant n-1
  participant n

  n-4->>n: ×(-1)
  n-3->>n: ×4
  n-2->>n: ×(-6)
  n-1->>n: ×4
  Note over n: a(n) = 4·a(n-1) - 6·a(n-2) + 4·a(n-3) - a(n-4)
  
```

---

## 14. Generating Function Decomposition - TODO

```mermaid
flowchart LR
    G[x]((G(x))) --> F1["x(1+x)²/(1-x)^4"]
    F1 -->|expand| T1["x + 6x² + 19x³ + 44x⁴ + ..."]
    
```

---

## 15. Connections to Other Mathematical Objects

```mermaid
---
title: "Connections to Other Mathematical Objects"
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
    O["A005900<br/>Octahedral"]
    O -- "binomial transform" --> C("Chebyshev Row 3:<br/> [1,5,8,4]")
    O -- "sum of centered squares" --> CS("A001844<br/>Centered Square Numbers")
    O -- "convolution square root" --> ON["A005408<br/>Odd Numbers"]
    O -- "difference" --> T("A000292<br/>Tetrahedral")
    O -- "difference" --> CU("A000578<br/>Cubes")
    
```

---

# Supplementary

## How to Compute - Algorithmic View

```mermaid
---
title: "How to Compute - Algorithmic View"
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
    Start(["Start"]) --> InputN["input:<br/>n"]
    InputN --> Comp1["Compute n*(2n^2+1)/3"]
    Comp1 --> Output["Return a(n)"]
    InputN --> AltComp["Alternatively:<br/>Sum 1^2 + 2^2 + ... + n^2 + ... + 1^2"]
    AltComp --> Output
    
```

---

# Summary Table: All Key Concepts

| Area              | Details/Formula                                                            |
| ----------------- | -------------------------------------------------------------------------- |
| Name/ID           | Octahedral Numbers (OEIS A005900)                                          |
| Explicit Formula  | $a(n) = n·(2n² + 1)/3$, or sum of squares as listed above                    |
| Geometric Meaning | Counts number of points in n-sized octahedron; part of Platonic number set |
| Recurrence        | $a(n) = 4·a(n-1) - 6·a(n-2) + 4·a(n-3) - a(n-4)$                          |
| Gen. Function     | OGF: $x(1+x)²/(1-x)^4$; EGF: $(1/3)x(3+6x+2x²)e^x$                           |
| Cross-references  | Cubes, Tetrahedral, Dodecahedral, Icosahedral, Odd numbers, etc.           |
| Combinatorics     | Connections to subsets, Young tableaux, group theory (Weyl groups)         |
| Programs          | Implemented in Python, Maple, Mathematica, Haskell, and more               |


---

**License and Attribution**

> - Mathematical data and exposition adapted from **The Online Encyclopedia of Integer Sequences** (<https://oeis.org/>), [OEIS sequence A005900](https://oeis.org/A005900), © OEIS Foundation Inc., licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) [![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-sa/4.0/).
> - Legal details in [LICENSE-CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0) and at [Creative Commons official site](https://creativecommons.org/licenses/by-sa/4.0/).
> - Diagram and explanatory code © 2025 Cong Le, **MIT License** [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) (for code **only**)- Full text in [LICENSE](LICENSE) file.  
>  
> - If you adapt, redistribute, or make derivative works involving *OEIS-based content*, you must retain this notice and apply **CC BY-SA 4.0**.

---

