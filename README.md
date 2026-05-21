This is a pacthed verison (uscs.R is updated) for rtracklayer on Biowulf compute node for R/4.5.2. 
The RestUri are not working well with proxy, replacing it with `httr`. There is a patch file rtracklayer-ucsc-json-compat.patch.

The default version will fail the test:
```
rtracklayer:::.test()

RUNIT TEST PROTOCOL -- Tue May 19 16:08:34 2026
***********************************************
Number of test functions: 11
Number of errors: 1
Number of failures: 0


1 Test Suite :
rtracklayer RUnit Tests - 11 test functions, 1 error, 0 failures
ERROR in test_ucsc: Error in normArgTable(value, x) : Table 'gold' is unavailable

Test files with failing tests

   test_ucsc.R
     test_ucsc


Error in BiocGenerics:::testPackage("rtracklayer") :
  unit tests failed for package rtracklayer
```

Clone the repo to local and install:
```
git clone https://github.com/qiyubio/rtracklayer.git
cd rtracklayer
R CMD INSTALL .
```
Run test again:
```
rtracklayer:::.test()
RUNIT TEST PROTOCOL -- Tue May 19 16:13:58 2026
***********************************************
Number of test functions: 11
Number of errors: 0
Number of failures: 0


1 Test Suite :
rtracklayer RUnit Tests - 11 test functions, 0 errors, 0 failures
Number of test functions: 11
Number of errors: 0
Number of failures: 0
There were 14 warnings (use warnings() to see them)
```
