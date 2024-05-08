Sumin Leem 2023

This repository contains magma files related to solving norm equations over global function fields, and testing scripts. This is with Magma V2.27-5 or later version.



    functions.mag
	- A collection of all necessary functions related to the algorithms 
	  for solving norm equations, including the algorithms related to
	  compact representations and S-Valuation matrices.

    testing_gen.mag
	- This file contains functions that generate random inputs for testings,
	  including polynomials of degree d of m distinct factors,
	  defining polynomials of degree n, and function fields F of the unit rank r,
	  of at least one degree 1 infinite place, 
	  F with unramified infinite place, etc.


-------------------------
 Correctness tests:
-------------------------

Testing files included are:

    Correctness/SValMat_Test.mag 
    Correctness/IsAssociate_Test.mag 

    Correctness/CompRep_Test.mag 
    Correctness/MultCR_Test.mag 
    Correctness/PowCR_Test.mag 
    Correctness/NormCR_Test.mag 

    Correctness/NE_GPCR_Test.mag 
    Correctness/NE_GP_Test.mag 
    Correctness/NE_PrincCR_Test.mag 


   *_Test.mag
	- This test codes test the correctness of the function using randomly 
	  generated inputs and precomputed inputs. This codes cover all possible
	  computation path in each function indicated in the file name.



-------------------------
 Timing tests:
-------------------------

Testing files included are:

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



    The names of directories indicate the parameter varied for the timing tests.
    (ex. Timing/cfactors contains testing files that are with the number of 
     distinct factors of c varied and the others (n, g, q, and deg(c)) are fixed.)

    Tests with different fixed parameters are tagged (ex. *_2.mag, *_3.mag,
     *_extra.mag, etc)



    FFlist_*.mag
	- The files include pre-generated inputs for the timing tests. A list of
	  global function fields and a list of polynomials c are in the file.
	  The function fields and c are generated using the functions in
	  testing_gen.mag.

    clistn_*.mag
	- The files include extra lists of polynomial c, that are pre-generated
	  using the functions in testing_gen.mag. 


    benchmark_GP_*.mag
	- This test codes are for timing tests of Gaal-Pohst method for solving
	  norm equations given in FFlist_*.mag and/or clistn_*.mag.

    benchmark_GPCR_*.mag
	- This test codes are for timing tests of the algorithm that is inspired
	  by Gaal-Pohst method and is using compact representations for solving
	  norm equations given in FFlist_*.mag and/or clistn_*.mag.

    benchmark_PrincCR_*.mag
	- This test codes are for timing tests of the principal ideal generator
	  algorithm for solving norm equations given in FFlist_*.mag 
	  and/or clistn_*.mag.



