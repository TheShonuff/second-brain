---
title: Two to One
creation date: 2022-12-13 10:53
aliases: []
tags: codewars 
---

# Two to One
Take 2 strings **s1** and **s2** including only letters from a to z. Return a new *sorted* string, the longest possible containing distinct letters - each taken only once - coming from **s1** or **s2**

**Success**:: false

### Solution
```Rust 
fn longest(a1: &str, a2: &str) -> String {
	let mut res: Vec<_> = a1.chars().collect();
	res.extend(a2.chars());
	res.sort();
	res.dedup();
	res.into_iter().collect()
}
```

**Notes**:: I was stuck on this one. The instructions were poorly written indicating you had to compare the strings when infact you had to combine them. The [extend](https://doc.rust-lang.org/std/iter/trait.Extend.html) [[Traits|trait]] allows an extension of a collection by using the contents of the iterator. Then the collection is sort and an iterator adpaptor called [Dedup](https://doc.rust-lang.org/std/iter/trait.Extend.html) is use to remove duplicates on the sorted iterator.
