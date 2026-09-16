---
name: ForEachWhile
slug: foreachwhile
sourceRef: slice.go#L212
category: core
subCategory: slice
signatures:
  - "func ForEachWhile[T any](collection []T, predicate func(item T, index int) bool) bool"
playUrl: https://go.dev/play/p/dG7h9H4nJQf
variantHelpers:
  - core#slice#foreachwhile
similarHelpers:
  - core#slice#foreach
  - core#slice#filter
  - core#slice#some
  - core#slice#every
  - core#slice#droprightwhile
  - core#slice#dropwhile
  - parallel#slice#foreach
position: 80
---

Iterates over elements of a collection and invokes the predicate for each element until false is returned. Returns true when the predicate returns true for every element, or false when any element returns false and iteration stops.

```go
numbers := []int64{1, 2, -9223372036854775808, 4}
allPositive := lo.ForEachWhile(numbers, func(x int64, _ int) bool {
    if x < 0 {
        return false
    }
    fmt.Println(x)
    return true
})
fmt.Println(allPositive)
// Output:
// 1
// 2
// false
```
