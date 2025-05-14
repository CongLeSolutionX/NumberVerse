 # NumberVerse
 ## A Curated Collection of Math & Computational Resources

This repository aggregates and visualizes mathematical resources and educational materials from multiple sources, each of which **may have its own license and legal requirements**.  
**Please review the license for each included resource before reuse, modification, or redistribution.**

---

## 📂 Repository Structure

```md
/resources
    /OEIS/
        <OEIS-content-files...>
        LICENSE-CC-BY-SA-4.0
    /Wikipedia/
        <Wikipedia-content-files...>
        LICENSE-CC-BY-SA-3.0
    /ThirdParty/
        <Third-party files...> 
        LICENSE-THIRDPARTY
    /Diagrams/
        <Custom-generated diagrams...>
    /Scripts/
        <Code and scripts...>
LICENSE  (for repo-level code, e.g. MIT)
README.md
```

---

## ⚖️ Licensing & Attribution Policy

### 1. **General Rule**

Each file or folder in `/resources` **includes a clear notice or header specifying:**
- The source/provider (e.g., OEIS, Wikipedia, Author/Project Name)
- The applicable license (with a link)
- Any required attribution statement
- Any Share-Alike or special terms

### 2. **Repo-wide Code License**

All **original code** in this repository (in `/Scripts` or similar) is licensed under [MIT License](LICENSE) (unless otherwise noted).

### 3. Resources by Source

#### A) OEIS Materials
- **Source**: [Online Encyclopedia of Integer Sequences (OEIS)](https://oeis.org/)
- **License**: [Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/)
- **Attribution Example**:  
  > Content/diagrams adapted from **The Online Encyclopedia of Integer Sequences**, https://oeis.org/, and [OEIS sequence Axxxxxx](https://oeis.org/Axxxxxx), © The OEIS Foundation Inc., used under CC BY-SA 4.0.

#### B) Wikipedia or Wikimedia Materials
- **Source**: [Wikipedia](https://wikipedia.org/) or Wikimedia Commons
- **License**: [Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/)
- **Attribution Required**: Include original article or media title, URL, and author as specified by Wikimedia.
- **Example**:  
  > Text/images adapted from [Wikipedia article: Fibonacci number](https://en.wikipedia.org/wiki/Fibonacci_number), licensed under CC BY-SA 3.0.

#### C) Third-party Open Source Code
- **License**: As specified in `/ThirdParty/<project>` (MIT, Apache, GPL, etc.)
- **Include**: License file or header in the folder
- **Example**:  
  > “This script includes/adapts code from [ProjectX](https://github.com/some/projectx) under the MIT License.”

#### D) Custom Diagrams & Notes
- **License**: By default, MIT (code/scripts), CC BY-SA 4.0 (creative works).
- **If containing OEIS/Wikipedia content**: Must inherit upstream license (typically CC BY-SA)

---

## 📝 How to Attribute When Reusing

- **Diagrams, text, or code**:  
  See the header of the file or the folder-specific LICENSE for how to attribute and which license applies.

---

## 📄 Legal Notice & Source Attribution

*   **License Compliance:** Your use of this repository signifies your agreement to adhere to all applicable source licenses and legal requirements.
*   **Content Usage:** For any content intended for commercial or non-open source applications, please diligently review the specific license associated with that content. If licensing terms are unclear, contact the original author or rights holder.
*   **Attribution & Corrections:** While every effort is made to ensure accurate attribution according to source licenses, errors or omissions may inadvertently occur. If you are an original author and believe your work has not been properly credited, please contact me at `conglejobs@gmail.com`. I am committed to promptly addressing any such concerns and ensuring appropriate citation.

---

## 🗂️ Contents

- **/resources/OEIS**: OEIS content and derived diagrams  
- **/resources/Wikipedia**: Wikipedia/Wikimedia sourced articles and images  
- **/resources/ThirdParty**: Various open source or third-party snippets/tools  
- **/resources/Diagrams**: Custom and composite diagrams  
- **/resources/Scripts**: Code for generation, analysis, and visualization  
- **LICENSE**: Main code license  
- **README.md**: This guide  



---
<!-- 
```mermaid
%% Current Mermaid version
info
``` 
-->


```mermaid

---
title: "CongLeSolutionX"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
  theme: base
---
%%{
  init: {
    'flowchart': { 'htmlLabels': false },
    'fontFamily': 'Brush Script MT',
    'themeVariables': {
      'primaryColor': '#fc82',
      'primaryTextColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#81c784',
      'secondaryTextColor': '#6C3483',
      'lineColor': '#F8B229',
      'fontSize': '20px'
    }
  }
}%%
flowchart LR
    My_Meme@{ img: "https://github.com/CongLeSolutionX/MY_GRAPHIC_ASSETS/blob/Designing_graphic_syntax/MY_MEME_ICONS/Orange-Cloud-Search-Icon-Base-Color-Black-1024x1024.png?raw=true", label: "Ăn uống gì chưa ngừi đẹp?", pos: "b", w: 200, h: 150, constraint: "on" }

    Closing_quote@{ shape: braces, label: "Math and code work together to bring interactive art to life!" }

My_Meme ~~~ Closing_quote

```

---