# Nikki - lab 1 - variant 4

A series of functional requirements are realized and tested based on
`hash map, separate chaining` method.

## Project structure

- `sc.py` -- Implementation of `Set` class based on hash map with separate chaining.
  Supports methods: `add`, `set`, `remove`, `size`, `member`, `reverse`,
  `from_list`, `to_list`, `filter`, `map`, `reduce`, `__iter__`, `__next__`,
  `empty`, `concat`.

- `sc_test.py` -- Unit and property-based tests for `sc`.

## Features

- **PBT Tests**:
   - `test_from_to_list_equivalence`
   - `test_size_equivalence`
   - `test_monoid_laws`

## Contribution

- **Lei Ningyu** (3232254146@qq.com) -- Implementation and testing.
- **Yi Min** (1757973489@qq.com) -- Implementation and testing.

## Changelog

- **22.02.2025 - v0**
   - Initial version.
- **22.02.2025 - v1**
   - Updated README, `sc.py`, and `sc_test.py`.
- **24.02.2025 - v2**
   - Revised README and modified `sc.py`, `sc_test.py`.
- **26.02.2025 - v3**
   - Finalized README and code optimizations.
- **02.03.2025 - v4**
   - Revised README and modified `sc.py`, `sc_test.py`.

## Design Notes

- **Separate Chaining Hash Map**:
   - Each bucket (array index) stores a linked list of key-value pairs.
   - Hash value modulo capacity determines the bucket index.
   - Duplicate values are rejected within the same bucket.

- **Reverse Operation**:
   - Initially, only bucket elements were reversed, causing test failures.
   - Correct approach: Reverse both bucket order and element order within each bucket.

- **None Handling**:
   - Tested adding `None` values in `sc_test.py` with no errors.
   - Implementation correctly handles `None` in all operations.

- **Monoid laws Test**:
   - Adding `Associativity` and `Identity element` test in `sc_test.py`.

## Analysis and Conclusion
- **Our implementation restrictions**:
   - The range of our function is still not very large, and the test cases don't cover the whole situations.
- **The advantages and disadvantages of unit test and PBT tests**:
   - The advantage of Unit test is that we can quickly find and fix problems. The downside is that we need to write a lot of use cases to ensure test coverage and prepare an operational environment for them.
   - The advantage of PBT test is that it can automatically generate a large number of test cases, which provides a broader guarantee of correctness than testing specific scenarios individually. The disadvantage is that random generation may not trigger true defects, resulting in false "pass" results.
