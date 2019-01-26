# INTRODUCTION
This is a header only very small library that I made to test some simple C++ code of mine.

# USAGE
Just include the file "FastSuite.hpp" under the "include/FastSuite" directory.

# EXAMPLE
```cpp
#include <iostream>
#include <errno.h>
#include "../include/FastSuite/FastSuite.hpp"

void TestSumWithAssert() {
    BEFORE() // Aways use BEFORE()
    int n1 = 1, n2 = 2, sum = n1 + n2;
    assert(3, sum);
    AFTER() // Aways use AFTER()
}

void TestSumWithException() {
    BEFORE() // Aways use BEFORE()
    int n1 = 3, n2 = 1 + 2, sum = n1 + n2;
    if (3 != sum) 
        throw std::runtime_error("Expected: " + std::to_string(3) + "; Found: " + std::to_string(sum));
    AFTER() // Aways use AFTER()
}

int main() {
    TestSumWithAssert();
    TestSumWithException();
    return 0;
}
```
