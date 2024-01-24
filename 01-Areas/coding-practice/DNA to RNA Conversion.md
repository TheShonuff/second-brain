---
title: DNA to RNA Conversion
creation date: 2022-12-24 15:33
aliases: []
tags: codewars 
---
# DNA to RNA Conversion
Deoxyribonucleic acid, DNA is the primary information storage molecule in biological systems. It is composed of four nucleic acid bases Guanine(G), Cytosine(C), Adeline(A) and Thymine(T).

Ribonucleic acid, RNA is the primary messenger molecule in cells. RNA differs slightly from DNA its chemical structure contains no Thymine. In RNA thymine is replaced by another nucleic adic Uracil(U)

Create a function which translates a given DNA string into RNA.

**Success**:: true

### Solution
```Rust
fn dna_to_rna(dna: &str) -> String {
	dna.chars().map(|x|
		match x {
			'T' => 'U',
			_ => x,
		}
	).collect()
}
```

**Notes**:: An easier one but I still had to look up a previous solution to see how to replace the chars. My inital if statement wasn't working with the chars to string conversion.

```Rust
fn dna_to_rna(dna: &str) -> String {
	dna.replace("T", "U")
}
```