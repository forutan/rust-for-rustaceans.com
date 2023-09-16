---
chapter: 1
page: 27
kind: code
reporter: Kyle Strand
date: 2023-08-27
---

Listing 2-3 reads:

```rust
impl String {
    pub fn contains(&self, p: &dyn Pattern) -> bool {
        p.is_contained_in(&*self)
    }
}
```

The `&*` before `self` has no effect and should be removed. The listing would then read:

```rust
impl String {
    pub fn contains(&self, p: &dyn Pattern) -> bool {
        p.is_contained_in(self)
    }
}
```
