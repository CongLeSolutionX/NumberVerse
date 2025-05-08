---
title: "Visualizing The On-Line Encyclopedia of Integer Sequences Wiki page - Draft"
author: Cong Le
created: 2025-05-08
version: 1.0
---


# Visualizing The On-Line Encyclopedia of Integer Sequences Wiki page - Draft

> **Source Attribution:**
>
> This document incorporates or adapts material from:
> - **The Online Encyclopedia of Integer Sequences** ([https://oeis.org/](https://oeis.org/))
> - The [OEIS Wiki Welcome page](https://oeis.org/wiki/Welcome)
> - © The OEIS Foundation Inc.
>
> **License:**
> 
> - **OEIS-derived content** (any mathematical data, structure, text, or visuals based on OEIS): **CC BY-SA 4.0**
> - If you adapt/redistribute these portions, you **must** provide attribution as above and license your derivative work under the same terms.
> - **Original diagram source code** (e.g., Mermaid, PlantUML, or script syntax BY CONG LE, not including OEIS math/data): **MIT License**, unless otherwise stated.
> - If you reuse just the code itself for unrelated subjects, **MIT** applies.

---




## 1. OEIS Ecosystem Overview

This mind map provides a high-level view of the OEIS, its components, and core purpose.

```mermaid
---
title: "OEIS Ecosystem Overview"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
---
%%{
  init: {
    'theme': 'base',
    'fontFamily': 'Monaco',
    'mindmap': {
      'padding': 20,
      'levelColors': ['#87CEEB', '#98FB98', '#FFDAB9', '#FFB6C1']
    },
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#145A32',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
%%%%%%%% Mermaid version v11.4.1-b.14
mindmap
  root((OEIS - The On-Line Encyclopedia of Integer Sequences®))
    Goal
      ::icon(fa fa-database)
      A comprehensive database of integer sequences
      A research tool for mathematicians and enthusiasts
      "Fingerprint file for number sequences"
    Supported By
      The OEIS Foundation Inc.
        ::icon(fa fa-donate)
        Owns, maintains, raises funds
    Key Components
      OEIS Main Database
        ::icon(fa fa-search)
        Search sequences
        View sequence entries
      OEIS Wiki
        ::icon(fa fa-book-open)
        Main Page (FAQ, Index, Style Sheet)
        User information
        Documentation
      Community
        Contributors
        Editors
        Users
        ::icon(fa fa-users)
    Famous Sequences Sampler
      Recamán's (A005132)
      Catalan Numbers (A000108)
      Prime Numbers (A000040)
      Fibonacci Numbers (A000045)
```

---

## 2. How Users Interact with OEIS

This flowchart illustrates the primary ways users can engage with the OEIS platform.

```mermaid
---
title: "How Users Interact with OEIS"
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
    'securityLevel': 'loose',
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#F5E3',
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
    User(["User"]) --> MainInteractions{"What do you want to do?"}

    MainInteractions -- Find Information --> Lookup
    Lookup["Look up a sequence"] --> BySequence{"Enter sequence terms?"}
    BySequence -- Yes --> SearchPage["Go to Main Look-up Page & Search"]
    SearchPage --> ResultsPage["View Sequence Entry /<br/> No Match"]
    ResultsPage -- "No Match & Stumped" --> Superseeker["Try Superseeker via Email"]
    BySequence -- "No,<br/> by name/keyword" --> SearchIndex["Search Index or Keywords on Look-up Page"]
    SearchIndex --> ResultsPage

    MainInteractions -- Explore --> Browse
    Browse[Browse OEIS] --> BrowseOptions{"Browse by..."}
    BrowseOptions -- Index --> IndexPage["Browse Full Index"]
    BrowseOptions -- WebCam --> WebCamPage["Use WebCam<br/>(Interesting, Recent, Needs Terms)"]
    BrowseOptions -- Special Categories --> SpecialCats["Puzzle /<br/> Classic /<br/> Hot Sequences"]
    BrowseOptions -- Recent Additions --> RecentPage["View Recent Additions"]

    MainInteractions -- Contribute --> ContributionFlow
    ContributionFlow["Contribute to OEIS"] --> RegisterCheck{"Registered User?"}
    RegisterCheck -- No --> Register["Register for an Account"]
    Register --> SubmissionPage
    RegisterCheck -- Yes --> SubmissionPage["Go to 'Contributing a new sequence or comment' Page"]
    SubmissionPage --> SubmitNew["Submit New Sequence /<br/> Comment /<br/> More Terms"]
    SubmitNew --> EditorialReview["Editor Review"]
    EditorialReview --> Published["Published in OEIS"]

    style User fill:#f9f,stroke:#333,stroke-width:2px
    style MainInteractions fill:#bdf,stroke:#333,stroke-width:2px
    
```


---

## 3. Anatomy of an OEIS Sequence Entry

This mind map details the various components and information typically found within an individual OEIS sequence entry page.

```mermaid
---
title: "Anatomy of an OEIS Sequence Entry"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
---
%%{
  init: {
    'theme': 'base',
    'fontFamily': 'Monaco',
    'mindmap': {
      'padding': 20,
      'levelColors': ['#87CEEB', '#98FB98', '#FFDAB9', '#FFB6C1']
    },
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#145A32',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
%%%%%%%% Mermaid version v11.4.1-b.14
mindmap
root(("OEIS Sequence Entry<br/>(e.g., Axxxxxx)"))
    ::icon(fa fa-list-ol)
    Core_Information("Core Information")
      Sequence Terms
        Beginning of the sequence
      Name/Description
        Formal name or descriptive text
      Offset
        Index of the first term listed
    Visuals_and_Audio("Visuals & Audio")
      Graph
        Pin_plot["Pin plot<br/>(first ~200 terms)"]
        Linear_log_scatter_plot["Linear/log scatter-plot<br/>(all terms)"]
      Listen
        MIDI file to hear the sequence
    Details_and_Context("Details & Context")
      Comments
        Additional notes, insights
      References/Links
        Citations, relevant web links
      Formulas
        Mathematical formulas generating the sequence
      Computer Programs
        Code_snippets["Code snippets<br/>(Maple, Mathematica, PARI, etc.)"]
      Cross-references
        Links to related OEIS sequences
    Metadata("Metadata")
      Submitter
        Name of the person who submitted it
      History
        Log of changes to the entry
      Internal Format
        Raw data structure view
    Interactive_Buttons("Interactive Buttons")
      "list"
        Numbered and bracketed term list
      "graph"
        Generates plots
      "refs"
        Shows sequences referencing this one
      "listen"
        Generates MIDI file
      "history"
        Shows entry change history
      "text"
        Shows entry sections with type prefixes
      "internal format"
        Displays internal data structure
      table["'table' <br/>(if applicable, e.g., for triangular arrays)"]
        Shows_2D_views["Shows 2D views (by Antti Karttunen)"]
      edit["'edit'<br/>(for registered editors/users)"]
      Proposechanges
      
```


----

## 4. OEIS Historical Milestones

This flowchart outlines the key events in the history of the OEIS.

```mermaid
---
title: "OEIS Historical Milestones"
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
    title OEIS Historical Milestones

    section Initial Beginning
    1964 : NJAS starts database on file cards (Cornell)
         : A000435 (first sequence) tracked
    1967 : Sequences transferred to punched cards
    1969 : NJAS joins AT&T Bell Labs
    1973 : "Handbook of Integer Sequences" published (2372 sequences)

    section Early 1990s
    Early 1990s : Significant correspondence on sequences
                : Simon Plouffe offers help

    1995 : "The Encyclopedia of Integer Sequences" published (5487 sequences)
    1996 : OEIS launched online on NJAS's AT&T page (10,000 entries)

    section Growth & Transition
    1996-2009 : Rapid growth (10k+ entries/year)
    2002 : Associate editors begin assisting(with limited access)
    2009 : The OEIS Foundation Inc. established
         : Intellectual Property (IP) transferred to Foundation
         : Initial attempt to use Mediawiki software runs into major problems

    section Rebuild & Relaunch
    2009-2010 : Russ Cox rewrites core OEIS software
              : David Applegate provides significant help
    Nov 11, 2010 : New OEIS system launched(wiki-like, ~130 editors)
                 : Community contributions fully enabled

    section Post-Relaunch Era
    Post-2010 : OEIS operates with community submissions and editorial review
              : Continues to be a vital resource
              
```

---

## 5. Contributing to OEIS and Getting Involved

This flowchart describes the process for contributing to the OEIS and other ways to help.

```mermaid
---
title: "Contributing to OEIS and Getting Involved"
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
    'securityLevel': 'loose',
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#F5E3',
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
    Start(("Want to Contribute?")) --> RegCheck{"Are you registered on OEIS?"}
    RegCheck -- No --> Register["Register an account on the OEIS Wiki"]
    RegCheck -- Yes --> ActionChoice{"What to contribute?"}
    Register --> ActionChoice

    ActionChoice -- new Sequence --> SubmitNewSeq["Submit a New Sequence"]
    ActionChoice -- comment --> SubmitComment["Submit a Comment to an Existing Sequence"]
    ActionChoice -- more terms --> SubmitTerms["Submit More Terms for an Existing Sequence"]

    subgraph SubmissionProcess["Submission Common Steps"]
        direction LR
        SubmitNewSeq --> Criteria["Check Criteria:<br/> Well-defined, General Interest, Infinite ideal"]
        Criteria --> Prep["Prepare submission via OEIS Submit.html page"]
        SubmitComment --> Prep
        SubmitTerms --> Prep
        Prep --> review["Editorial Review Process"]
        Review -- approved --> Publish["Published to OEIS"]
        Review -- needs Revision --> Prep
    end

    Start --> HelpMethods{"Other ways to help?"}
    HelpMethods --> MoreTerms["Work on<br/> 'Sequences that need more terms'"]
    MoreTerms --> ViaLink["Access via<br/> '/more.html'"]
    MoreTerms --> ViaWebCam["Use WebCam to find them"]
    MoreTerms --> ViaSearch["Search for keyword 'more"]
    HelpMethods --> FutureProj["Check <br/>'future projects' page<br/>(needs update)"]

    style Start fill:#f222,stroke:#333,stroke-width:2px
    style SubmissionProcess fill:#ef26,stroke:#333,stroke-width:1px
    
```



----

## 6. OEIS Data, Resources, and Citation

This mind map covers downloadable data, reference books, and how to cite the OEIS.

```mermaid
---
title: "OEIS Data, Resources, and Citation"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
---
%%{
  init: {
    'theme': 'base',
    'fontFamily': 'Monaco',
    'mindmap': {
      'padding': 20,
      'levelColors': ['#87CEEB', '#98FB98', '#FFDAB9', '#FFB6C1']
    },
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#145A32',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
%%%%%%%% Mermaid version v11.4.1-b.14
mindmap
root(("OEIS Data, Resources &<br/> Citation"))
::icon(fa fa-archive)
    Published Books("Published Books<br/>(Foundational Texts by NJAS et al.)")
        Handbook_of_Integer_Sequences["'Handbook of Integer Sequences'<br/>(1973)"]
        ::icon(fa fa-book)
        
        Introductory_Chapters["Introductory Chapters<br/>(PDF)"]
        Supplement_3["Supplement 3<br/>(TXT)"]
        
        Encyclopedia_of_Integer_Sequences["'Encyclopedia of Integer Sequences'<br/>(1995)"]
        ::icon(fa fa-book)

        Introductory_Chapters["Introductory Chapters<br/>(PDF)"]

    Downloadable_Data("Downloadable Data<br/>(Updated Daily)")
        stripped_gz("'stripped.gz'")
            Gzipped file
            Sequences_and_A_numbers["Sequences & A-numbers"]
        names_gz("'names.gz'")
            Gzipped file
            Sequences_and_A_numbers["Sequences & A-numbers"]
    Citing_OEIS("Citing OEIS")
        General OEIS Citation
            Format["Format:<br/>OEIS Foundation Inc. (Year),<br/>The On-Line Encyclopedia of Integer Sequences,<br/>Published electronically at https://oeis.org"]
        Referencing_a_Specific_Sequence["Referencing a Specific Sequence<br/>(e.g., A000108)"]
            URL["URL: https://oeis.org/A000108"]
            Text_Reference_Example["Text Reference Example:<br/> *The On-Line Encyclopedia of Integer Sequences*, ..., Sequence A000108"]
            HTML_Link_Example["HTML Link Example"]
    Other_Resources("Other Resources")
        Index to OEIS
        Hints File
        eishelp2_html["'eishelp2.html'<br/>(Format of replies)"]
        Works Citing OEIS
        
```


---

## 7. OEIS Community, Support, and Communication

This mind map focuses on how to interact with the OEIS community and find support.

```mermaid
---
title: "OEIS Community, Support, and Communication"
author: "Cong Le"
version: "1.0"
license(s): "MIT, CC BY-SA 4.0"
copyright: "Copyright (c) 2025 Cong Le. All Rights Reserved."
config:
---
%%{
  init: {
    'theme': 'base',
    'fontFamily': 'Monaco',
    'mindmap': {
      'padding': 20,
      'levelColors': ['#87CEEB', '#98FB98', '#FFDAB9', '#FFB6C1']
    },
    'themeVariables': {
      'primaryColor': '#D5F5E3',
      'primaryTextColor': '#145A32',
      'lineColor': '#F8B229',
      'primaryBorderColor': '#27AE60',
      'secondaryColor': '#EBDEF0',
      'secondaryTextColor': '#6C3483',
      'secondaryBorderColor': '#A569BD',
      'fontSize': '20px'
    }
  }
}%%
%%%%%%%% Mermaid version v11.4.1-b.14
mindmap
root(("OEIS Community & Support"))
::icon(fa fa-hands-helping)
    Contacting_Authors_Contributors["Contacting Authors/Contributors"]
        Old_Method("Old Method<br/>(NJAS Homepage OEIS)")
            Disguised_email_addresses["Disguised email addresses<br/>(essential for scientific database)"]
        Current_OEIS_Wiki_Method("Current OEIS Wiki Method")
		    Step_1["Step 1:<br/>Log in to OEIS Wiki"]
		    Step_2["Step 2:<br/>Find author in 'Registered Users' list"]
		    Step_3["Step 3:<br/>Go to author's User Page"]
		    Step_4["Step 4:<br/>Click 'Email this user'<br/>(left panel)"]
    Ombudsman("Ombudsman")
    ::icon(fa fa-balance-scale)
        Hilarie Orman
        Helps resolve disputes with contributors
        Contact via her User Page on the Wiki
    The_OEIS_Foundation_Inc("The OEIS Foundation Inc.")
    ::icon(fa fa-building)
        Owns, maintains, and supports OEIS
        Non-profit organization
        Accepts donations
    Editorial_Team("Editorial Team")
    ::icon(fa fa-users-cog)
        ~130 editors (as of 2010 launch)
        Review submissions for new sequences and updates
    SeqFan_Google_Group("SeqFan Google Group")
    ::icon(fa fa-comments)
        Discussion forum for sequence enthusiasts
      
```


---

## 8. OEIS Recognition and Impact

Highlights of mentions, awards, and quotes showcasing the OEIS's significance.

```mermaid
---
title: "OEIS Recognition and Impact"
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
    'securityLevel': 'loose',
    'flowchart': { 'htmlLabels': true, 'curve': 'linear' },
    'fontFamily': 'Monaco',
    'themeVariables': {
      'primaryColor': '#F5E3',
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
    subgraph Media_and_Pop_Culture["Media &<br/> Pop Culture"]
        TV_MrRobot["Mr. Robot<br/>(TV Series, S2 E11/12)"]
        Movie_OEIS["OEIS:<br/>The Movie<br/>(Tony Noe)"]
    end

    subgraph Publications_and_Articles["Publications &<br/> Articles"]
    direction TB
        PythagorasMag["Pythagoras Magazine<br/>(Dutch)"]
        CabinetMag["Cabinet Magazine<br/>(Interview with NJAS)"]
        NautilusMag["Nautilus Magazine<br/>(Article on OEIS)"]
        QuantaMag["Quanta Magazine<br/>(Interview with NJAS)"]
        GuardianBlog["The Guardian Blog<br/>(Alex Bellos)"]
        MalayalamPaper["Malayalam Newspaper Article"]
    end

    subgraph Academic_and_Technical_Community["Academic &<br/> Technical Community"]
    direction TB
        EricEgge["Eric Egge Quote<br/>(Impact on Combinatorics)"]
        Slashdot["Slashdot Feature"]
        HackerNews["Hacker News Discussion"]
        WolframTimeline["WolframAlpha Timeline Mention<br/>(under 1973)"]
        JMM_Interview["Joint Math Meetings Interview<br/>(Video)"]
    end

    subgraph General_Recognition["General Recognition"]
        AwardsPage["Awards and Press Clippings Page<br/>(Full list)"]
    end

    Media_Pop_Culture --> AwardsPage
    Publications_Articles --> AwardsPage
    Academic_Technical_Community --> AwardsPage

    style Media_Pop_Culture fill:#f68c,stroke:#311,stroke-width:1px
    style Publications_Articles fill:#ade6,stroke:#333,stroke-width:1px
    style Academic_Technical_Community fill:#990,stroke:#333,stroke-width:1px
    style General_Recognition fill:#4dd,stroke:#333,stroke-width:1px
    
```


---

**License and Attribution**

> - Mathematical data and exposition adapted from **The Online Encyclopedia of Integer Sequences** (<https://oeis.org/>), [OEIS Wiki Welcome Page](https://oeis.org/wiki/Welcome), © OEIS Foundation Inc., licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) [![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-sa/4.0/).
> - Legal details in [LICENSE-CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0) and at [Creative Commons official site](https://creativecommons.org/licenses/by-sa/4.0/).
> - Diagram and explanatory code © 2025 Cong Le, **MIT License** [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) (for code **only**)- Full text in [LICENSE](LICENSE) file.  
>  
> - If you adapt, redistribute, or make derivative works involving *OEIS-based content*, you must retain this notice and apply **CC BY-SA 4.0**.

---

