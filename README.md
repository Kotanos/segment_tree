Segment Tree with range operations
========================================

![LicenseLink](https://img.shields.io/badge/license-MIT-blue.svg)

This is a general implementation of a segment tree for Python 3.

* Semigroup range operations in O(logN) time
* Built-in support for `max`, `min`, `sum` functions
* Extensible to support more semigroup operations
* Only Python 3 for now

Example usage
============
## Basic queries
```python

    array = [3, 1, 5, 3, 13, 7, 2, 7, 2]
    tree = SegmentTree(array)

    t.query(1, 3, "sum") # 9
    t.update(0, 10) # [10, 1, 5, 3, 13, 7, 2, 7, 2]
    t.query(0, 8, "min") # 0
    t.update(2, -1) # [10, 1, -1, 3, 13, 7, 2, 0, 2]
    t.query(0, 2, "min") # -1
```
## Updates on ranges
```python
    array = [1, 2, 3, 4, 5]
    t = SegmentTree(array)
    t.update_range(0, 2, 6) # 6 6 6 4 5
    t.update_range(1, 4, 2) # 6 2 2 2 2
    t.query(0, 3, "min") # 2
```

Installation
============

`pip3 install segment-tree`

Supported operations and complexity
============
| Function | Description | Complexity | Additional storage
| ------ |---------|----------:|------:
| `SegmentTree(array)` | Builds a segment tree from an `array` | O(n log n) | O(n log n)        
| `update(position, value)` | Updates an old value at `position` to `value`| O(log n) | O(1)
| `update_range(start, end, value)` | Sets `value` on a `[start, end]` range | O(log n) | O(1)
| `query(start, end, function)` | Returns `function([start, end])`| O(log n) | O(1)


Tests
=====
Execute `python3 setup.py test` to run tests.