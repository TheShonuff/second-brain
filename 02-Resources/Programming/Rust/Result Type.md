---
title: Result Type
creation date: 2022-12-07 10:56
aliases: []
tags: rust filed
---

# Result Type

is used when something has a useful result or error. Like [[Option Type]], it's an [[Enums| enumerated type]] with two possible variants.
1. Ok(*T*) - Meaning the operation succeeded with value *T*
2. Err(*E*) - Meaining the operation failed with an error *E*
