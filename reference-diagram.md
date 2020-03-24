# Reference

## Sequece Diagram

```sequence-diagram
Alice -> Bob : Authentication Request
Bob --> Alice : Authentication Response

Alice -> Bob : Another authentication Request
Bob --> Alice : another authentication Response
```

## State Diagram

```mermaid
stateDiagram
    [*] --> Still
    Still --> [*]
%% this is a comment
    Still --> Moving
    Moving --> Still %% another comment
    Moving --> Crash
    Crash --> [*]
```

## Flowchart

```mermaid
graph TD
A[Christmas] -->|Get money| B(Go shopping)
B --> C{Let me think}
C -->|One| D[Laptop]
C -->|Two| E[iPhone]
C -->|Three| F[Car]
```