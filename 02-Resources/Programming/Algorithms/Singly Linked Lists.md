---
title: Singly Linked Lists
creation date: 2022-12-18 23:14
aliases: 
tags:
  - cs
  - algorithms
---

# Singly Linked Lists
A data structure that contains a **head**, **tail**, and **length** property. 

Linked lists consist of nodes, and each node has a value and a pointer to another node or null.

- Do not have index
- Connected via nodes with ta **next** pointer
- Random access is not allowed.

> [!tip] if **insertion** and **deletion** are important this is a good data structure to use

```js
class Node {
	constructor(val){
		this.val = val;
		this.next = null;
	}
}

class SinglyLinkedList {
	constructor(){
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	push(val){
		var newNode = new Node(val);
		if(!this.head){
			this.head = newNode;
			this.tail = this.head;
		} else {
			this.tail.next = newNode;
			this.tail = newNode;
		}
		this.length++;
		return this;
	}
	pop(){
		if(!this.head) return undefined;
		var current = this.head;
		var newTail = current;
		while(current.next){
			newTail = current;
			current = current.next;
		}
		this.tail = new.Tail;
		this.tail.next = null;
		this.length --;
		if(this.length === 0){
			this.head = null;
			this.tail = null;
		}
		return current;
	}
}
```


# Rust Singly Linked List
[Reference](https://rtoch.com/posts/rust-singly-linked-list/)
```Rust
struct ListNodeValue<T> {
	item: T,
	next: Box<ListNode<T>>,
}

imple<T> ListNodeValue<T> {
	fn new(item: T, next: Box<ListNode<T>>) -> Self {
		Self { item, next}
	}
}

enum ListNode<T> {
	Empty,
	NonEmpty(ListNodeValue<T>),
}

impl<T> ListNode<T> {
	fn new(item: T, next: Box<ListNode<T>>) -> Self {
		ListNode::NonEmpty(ListNodeValue::new(item, next))
	}
	fn take(&mut self) -> Self {
		let mut cur = Self::Empty;
		std::mem::swap(&mut cur, self);
		cur
	}
}
```