---
title: AWK
tags: [bash, shell]
aliases: []
date: 2023-09-11
---

`pattern { action }`

```mermaid
stateDiagram-v2

line: Line of Awk \n code
pattern: Pattern \n matches?
action: Execute Action
next: Go next line

line --> pattern
pattern --> action: yes
pattern --> next: no
action --> next
next --> line
```

pattern | summary
--- | ---
`BEGIN { statement }` | The `statement` are executed once before any input has been read
`END { statement }` | The `statement` are executed once after all input has been read
`expression {}`