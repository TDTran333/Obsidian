---
tags: mermaid
---
Link: [Website](https://mermaid-js.github.io/mermaid/#/), [YouTube](https://www.youtube.com/watch?v=rXhUeV5Ko7g)
### Diagrams that mermaid can render
### [](Diagrams%20Types.md#/?id=flowchart)[Flowchart](https://mermaid-js.github.io/mermaid/#/flowchart?id=flowcharts-basic-syntax)
TD = Top Down
```mermaid
graph TD
    A[Christmas] -->|Get money| B(Go shopping)
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
```

Direction
TB
BT
LR
RL

### [Sequence diagram](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)

```mermaid
sequenceDiagram
	participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

### [Gantt diagram](https://mermaid-js.github.io/mermaid/#/gantt)

```mermaid
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram to mermaid
excludes weekdays 2014-01-10
    
section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2              :         des4, after des3, 5d
```

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       Adding GANTT diagram functionality to mermaid
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2              :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :1d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      :20h
    Add another diagram to demo page    :48h
```

### [Class diagram](https://mermaid-js.github.io/mermaid/#/classDiagram)

```mermaid
classDiagram
Class01 <|-- AveryLongClass : Cool
Class03 *-- Class04
Class05 o-- Class06
Class07 .. Class08
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
Class08 <--> C2: Cool label
```

### [Git graph - ! experimental](https://mermaid-js.github.io/mermaid/#/?id=git-graph-exclamation-experimental)

```mermaid
gitGraph:
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```

### [Entity Relationship Diagram - !experimental](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram)
```mermaid
erDiagram
	CUSTOMER }|..|{ DELIVERY-ADDRESS : has
	CUSTOMER ||--o{ ORDER : places
	CUSTOMER ||--o{ INVOICE : "liable for"
	DELIVERY-ADDRESS ||--o{ ORDER : receives
	INVOICE ||--|{ ORDER : covers
	ORDER ||--|{ ORDER-ITEM : includes
	PRODUCT-CATEGORY ||--|{ PRODUCT : contains
	PRODUCT ||--o{ ORDER-ITEM : "ordered in"  
```    

### [User Journey Diagram](https://mermaid-js.github.io/mermaid/#/user-journey)

```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

### Pie chart

```mermaid
pie
"Dogs" : 45
"Cats" : 85
"Rats" : 15
```

### classDiagram

```mermaid
classDiagram
Class01 <|-- AveryLongClass : Cool
<<interface>> Class01
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
class Class10 {
  <<service>>
  int id
  size()
}
```


### stateDiagramv2

```mermaid
stateDiagram-v2
[*] --> Still
Still --> [*]
Still --> Moving
Moving --> Still
Moving --> Crash
Crash --> [*]
```

### Other examples

```mermaid
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A
        od>Odd shape]-- Two line<br/>edge comment --> ro
        di{Diamond with <br/> line break} -.-> ro(Rounded<br>square<br>shape)
        di==>ro2(Rounded square shape)
    end

    %% Notice that no text in shape are added here instead that is appended further down
    e --> od3>Really long text with linebreak<br>in an Odd shape]

    %% Comments after double percent signs
    e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز)

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

     classDef green fill:#9f6,stroke:#333,stroke-width:2px;
     classDef orange fill:#f96,stroke:#333,stroke-width:4px;
     class sq,e green
     class di orange
```

### Timeline

```mermaid
gantt
dateFormat YYYY
axisFormat  %Y

ca. 1420-1450                       :crit, 1420,1450
Guillaume Du Fay                    :, 1397,1474
Gilles Binchois                     :, 1400,1460

ca. 1450-1480                       :crit, 1450,1480
Antoine Busnois                     :, 1432,1492
Johannes Ockeghem                   :, 1439,1497

ca. 1480-1520                       :crit, 1480,1520
Adrian Willaert                     :, 1490,1562
Nicolas Gombert                     :, 1495,1560
Jacob Clemens non Papa				:, 1510,1555

ca. 1520-1550                   	:crit, 1520,1550
Philipp de Monte                    :, 1521,1603
Giovanni Pierluigi da Palestrina    :, 1525,1594
Orlande de Lassus                   :, 1532,1594
```

```mermaid
graph LR;
    A-->B[AAA];
    B-->D;

    %% Class Definitions
    %% =================
    class A cssClass;
    classDef cssClass fill:#f9f,stroke:#333,stroke-width:4px, font-size:15px;
```

```mermaid

graph LR;

%% Class Definitions
%% =================

classDef FixFont font-size:11px;

%% Nodes
%% =====

QuickStart(Quick Start):::FixFont -->
    CmdPalette(Command<BR>Palette):::FixFont;
QuickStart --> 
    CreateNotes("Create notes"):::FixFont;
QuickStart --> 
    InternalLinks("Internal Links"):::FixFont;

click CreateNotes "/Create notes";
click CmdPalette "/Command palette";
click InternalLinks "/Internal link";

%% Internal links
%% ==============

class CmdPalette internal-link;
class CreateNotes internal-link;
class InternalLinks internal-link;

%% Node styles
%% ===========

style CmdPalette fill:#383;  
style QuickStart fill:#A00;
style CreateNotes fill:#03C;
style InternalLinks fill:#C097;
```

```mermaid
graph LR;
bash --> onedrive --> systemctl;

click bash "obsidian://vault/Obsidian/bash";
click onedrive "obsidian://vault/Obsidian/onedrive";
click systemctl "obsidian://vault/Obsidian/systemctl";
```

https://mermaid-js.github.io/mermaid/#/classDiagram?id=styling
https://github.com/mermaidjs/mermaid-gitbook/blob/master/content/flowchart.md#styling-a-node