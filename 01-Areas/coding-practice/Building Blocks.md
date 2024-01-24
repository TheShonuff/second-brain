---
title: Building Blocks
creation date: 2023-02-05 23:27
aliases: []
tags: codewars 
---
# Building Blocks
Write a class **block** that creates a **block**. The constructor shoudl take an array as an argument, this will contain 3 integers of the from [width, length, height] from which the **block** should be created

**Success**:: true

### Solution
```Rust
#[derive(Debug)]
struct Block  {
    width: u32,
    length: u32,
    height: u32,
}
impl Block {
    fn new(arr: &[u32]) -> Block {
        Block  {
            width: arr[0],
            length: arr[1],
            height: arr[2],
        }
    }
    fn get_width(&self) -> u32 {
        self.width
    }
    fn get_height(&self) -> u32{
        self.height
    }
    fn get_length(&self) -> u32 {
        self.length
    }
    fn get_volume(&self) -> u32 {
        self.width * self.height * self.length
    }
    fn get_surface_area(&self) -> u32 {
        2*((self.width * self.length) + (self.length * self.height) + (self.width * self.height))
    }
}
```

**Notes**:: First challenge actually implementing object style in Rust. I definetly require more practice in this area and it was interesting implementing what I knew so far. The error I made in this challange was using the wrong integer type. My first submission used signed integers when the solution only accepted unsigned integers. The requirment was listed in the description and I missed it.

There was no real difference in my solution and the other accepted solutions other than minor syntax differences.