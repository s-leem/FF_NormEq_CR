# Norm Equation Algorithms over Global Function Fields

Research implementation, correctness tests, and benchmarking code for algorithms developed in **“Solving Norm Equations in Global Function Fields.”**

This repository contains Magma implementations of algorithms for solving norm equations over global function fields. It also includes randomized and precomputed correctness tests, input-generation utilities, computational examples, and benchmark suites comparing the proposed algorithms with the Gaál–Pohst method.

## What This Repository Includes

* Implementations of the core norm-equation algorithms
* Compact-representation and S-valuation-matrix operations
* Random and precomputed test-input generation
* Correctness tests covering different computational paths
* Runtime benchmarks across varying field and input parameters
* Computational examples accompanying the research

## Requirements

* Magma V2.27-5 or later

## Repository Structure

### Core Implementation

* `functions.mag`
  Core functions used by the norm-equation algorithms, including compact representations and S-valuation matrices.

* `testing_gen.mag`
  Utilities for generating random function fields, polynomials, and other test inputs.

* `Examples.mag`
  Computational examples illustrating the algorithms.

### Correctness Tests

The `Correctness/` directory contains randomized and precomputed tests for the main components and algorithms. The tests are designed to exercise different computational paths and verify the correctness of the implementation.

Testing files included are:

```text
Correctness/SValMat_Test.mag
Correctness/IsAssociate_Test.mag

Correctness/CompRep_Test.mag
Correctness/MultCR_Test.mag
Correctness/PowCR_Test.mag
Correctness/NormCR_Test.mag

Correctness/NE_GPCR_Test.mag
Correctness/NE_GP_Test.mag
Correctness/NE_PrincCR_Test.mag
```

#### `*_Test.mag`

These test files verify the correctness of the corresponding functions using randomly generated and precomputed inputs. The tests cover all possible computational paths in each function indicated by the file name.

### Timing Benchmarks

The `Timing/` directory contains benchmark inputs and scripts for comparing:

* The Gaál–Pohst method
* A Gaál–Pohst-inspired method using compact representations
* The principal-ideal-generator approach

The subdirectories vary one primary parameter while holding the others fixed:

* `n/`: extension degree
* `g/`: genus
* `q/`: constant-field size
* `degc/`: degree of the norm target
* `cfactors/`: number of distinct factors of the norm target

Files named `FFlist_*.mag` and `clistn_*.mag` contain pregenerated benchmark inputs.

Testing files included are:

```text
Timing/n/FFlist_n.mag
Timing/n/benchmark_GP_n.mag
Timing/n/benchmark_GPCR_n.mag
Timing/n/benchmark_PrincCR_n.mag

Timing/n/FFlist_n_2_3.mag
Timing/n/clistn_2.mag
Timing/n/benchmark_GPCR_n_2.mag
Timing/n/benchmark_PrincCR_n_2.mag

Timing/n/clistn_3.mag
Timing/n/benchmark_PrincCR_n_3.mag

Timing/g/FFlist_g_small.mag
Timing/g/benchmark_GP_g_small.mag
Timing/g/benchmark_GPCR_g_small.mag
Timing/g/benchmark_PrincCR_g_small.mag

Timing/g/FFlist_g.mag
Timing/g/benchmark_PrincCR_g.mag

Timing/q/FFlist_q.mag
Timing/q/benchmark_GP_q.mag
Timing/q/benchmark_GPCR_q.mag
Timing/q/benchmark_PrincCR_q.mag

Timing/degc/FFlist_c.mag
Timing/degc/benchmark_GP_c.mag
Timing/degc/benchmark_GPCR_c.mag
Timing/degc/benchmark_PrincCR_c.mag

Timing/degc/FFlist_c_2.mag
Timing/degc/benchmark_GPCR_c_2.mag
Timing/degc/benchmark_PrincCR_c_2.mag

Timing/degc/FFlist_c_extra.mag
Timing/degc/benchmark_PrincCR_c_extra_15bitc.mag

Timing/cfactors/FFlist_facc_degc10.mag
Timing/cfactors/benchmark_GP_cfactors10.mag
Timing/cfactors/benchmark_GPCR_cfactors10.mag
Timing/cfactors/benchmark_PrincCR_cfactors10.mag

Timing/cfactors/FFlist_facc.mag
Timing/cfactors/benchmark_GPCR_cfactors.mag
Timing/cfactors/benchmark_PrincCR_cfactors.mag
```

The directory names indicate the parameter varied in the timing tests. For example, `Timing/cfactors/` contains testing files in which the number of distinct factors of `c` is varied while the other parameters, `n`, `g`, `q`, and `deg(c)`, are fixed.

Tests with different fixed parameters are tagged with suffixes such as `_2`, `_3`, and `_extra`.

#### `FFlist_*.mag`

These files contain pregenerated inputs for the timing tests, including a list of global function fields and a list of polynomials `c`. The function fields and polynomials are generated using the functions in `testing_gen.mag`.

#### `clistn_*.mag`

These files contain additional pregenerated lists of polynomials `c`, generated using the functions in `testing_gen.mag`.

#### `benchmark_GP_*.mag`

These files contain timing tests for the Gaál–Pohst method for solving the norm equations defined in the corresponding `FFlist_*.mag` and/or `clistn_*.mag` files.

#### `benchmark_GPCR_*.mag`

These files contain timing tests for the algorithm inspired by the Gaál–Pohst method and using compact representations to solve the norm equations defined in the corresponding `FFlist_*.mag` and/or `clistn_*.mag` files.

#### `benchmark_PrincCR_*.mag`

These files contain timing tests for the principal ideal generator algorithm for solving the norm equations defined in the corresponding `FFlist_*.mag` and/or `clistn_*.mag` files.

## Reproducibility

This repository contains the research code used to test correctness and evaluate the computational performance of the algorithms. It is intended as a reproducible research artifact rather than a production software package.

## Reference

Sumin Leem, Michael J. Jacobson Jr., and Renate Scheidler, **[Solving Norm Equations in Global Function Fields](https://link.springer.com/article/10.1007/s40993-024-00606-6)**, *Research in Number Theory*, 11, Article 17 (2025).
