# Problem
(Not guaranteed to be truth) Cpp compiler works with each file consequtively. It means that the compiler can't see `bar.cpp` and `foo.cpp` at the same time, thus sometimes there's a trouble that linker doesn't see any instantiation of a function/class.
# Solution
As far as I see there're 2 general solutions for this problem:
1. You know exactly what instantiations will be used.
   Then, google for `extern template` (available since C++11)
3. You don't know what instantiations will be needed by a user
   You need to put a template definition inside of a header where it is declared. For this reason, my best practice is to make a special folder `tsrc` with files which have `.tpp` extension and they're simply included to the bottom of a header by `#include "tsrc/file_name.tpp"`.
