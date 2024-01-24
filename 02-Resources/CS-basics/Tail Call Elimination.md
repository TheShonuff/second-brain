---
tags:
  - cs
---
# Tail Call Elimination
In computer science a tail call is a subroutine performed as the final action of procedure. If the target of a tail is the same subroutine then it's **tail recursive**.

These calls can be implemented *without* adding to the [[call stack]]. The current procedure is no longer needed and can be replaced by the tail. This is called [[Tail Call Elimination]]. They're essentially goto statements allowing for efficient structure programming. 