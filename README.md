# Multi-unit production planning with integer and continuous variables
##### An optimization test suite involving 162 integer and 108 continuous variables

This submission can be used to evaluate the performance of optimization techniques on problems with integer and continuous variables. This optimization problem arises for maximization of profit in production planning. However these files can be used as black-box optimization problems.

There are eight minimization optimization problems in this suite (case1.p, case2.p, case3.p, case4.p, case5.p, case6.p, case7.p and cas8.p).

Each of them has the following format
```
[ F, XCorrected] = case1(X);
```
Input: population (or solution, denoted by X) and its <br/>
Output: (i) the corrected population (denoted by XCorrected), and <br/>
        (ii) the objective function value of the corrected population members (F). X is corrected to XCorrected as most algorithms fail to satisfy the complex constraints and XCorrected is not worse to X.

The file ProblemDetails.p can be used to determine the lower and upper bounds along with the function handle for each of the cases.

The format is `[lb, ub, fobj] = ProblemDetails(ca);`

Input: ca is an integer from 1 to 8. <br/>
Output: (i) the lower bound (lb), <br/>
        (ii) the upper bound (ub), and <br/>
        (iii) function handle (fobj).

The file Script.m shows how to use these files along with an optimization algorithm (SanitizedTLBO).

All cases (Case1 to Case 8) have a problem dimension of 270 variables. The first 162 variables are integer whereas the remaining 108 variables are continuous. If the first 162 values are continuous, these are rounded to the nearest integer using the round function of MATLAB.

**Note:**

  1. The inbuilt optimization algorithms in MATLAB require that the objective function file return only the values of the objective function and cannot be directly used to solve these problems.

  2. Conventionally, the algorithm provides the solutions (X) and requires the objective function values (F). But in these problems, in addition to F, the corrected solutions (XCorrected) are provided by the objective function file.

  3. The current best known solutions (rounded to two decimals), using computational intelligence algorithms, are <br />
  Case 1: -722.71; Case 2: -852.69; Case 3: -1284.40; Case 4: -1510.85 <br />
  Case 5: -734.66; Case 6: -844.35; Case 7: -1257.14; Case 8: -1481.30

  4. Case 1 - 4 have the same problem structure but employ different data; Case 5 - 8 has same set of data as compared to Case 1 - 4, but do not employ a certain feature (flexible) of the problem.

  5. The objective function files are capable of determining the objective function values of multiple solutions (i.e., if required, the entire population can be sent to the objective function file).

**Reference:** S.S. Chauhan, et al., A novel strategy for the combinatorial production planning problem using integer variables and performance evaluation of recent optimization algorithms, Swarm and Evolutionary Computation (2018), 
https://doi.org/10.1016/j.swevo.2018.04.004 
