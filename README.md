# CPP Con
## 2024

### [What’s Eating my RAM? - C++ Memory Management - Jianfei Pan](https://www.youtube.com/watch?v=y6AN0ks2q0A)
Talk about why a service could use more and more ram in time or more than expected. Talk about mamory leak and memory fragmentation, and tools and methods to detect it.

### [Hidden Overhead of a Function API - Oleksandr Bacherikov](https://www.youtube.com/watch?v=PCP3ckEqYK8&list=PLHTh1InhhwT6U7t1yP2K8AtTEKmcM3XU_&index=16)
Type of parameters, numbers and use order may influence generated compiled code and performance and in contradiction to core guidelines. Always measure

### [Back to Basics: Unit Testing in C++ - Dave Steffen - CppCon](https://www.youtube.com/watch?v=MwoAM3sznS0&list=PLHTh1InhhwT6U7t1yP2K8AtTEKmcM3XU_&index=7)
What is unit test? Why unit test? Black box/white box. Better bad tests than no test. No test can lead to project failure, bad tests can at least catch some bugs, and you learn.

### [Back to Basics: Almost Always Vector - Kevin Carpenter](https://www.youtube.com/watch?v=VRGRTvfOxb4)
Why vector exists at all compared to C-style array. General (or not) information on how a vector behave, some use case, and some counter cases.
for-range loop copy values, beware.
## 2023
###  [Continuous Regression Testing for Safer and Faster Refactoring in C++ - Pejman Ghorbanzade - CppCon](https://www.youtube.com/watch?v=c8Z3iSL9vYs&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=21)
Talk about testing and demonstration of Tuca OSS for test regression. Tuca capture the state of an application to compare it between different runs at different commits.

### [Delivering Safe C++ - Bjarne Stroustrup - CppCon 2023](https://www.youtube.com/watch?v=I8UvQKvOSSw&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=6&pp=iAQB)
Good keynote

### [Customization Methods: Connecting User and C++ Library Code - Inbal Levi](https://www.youtube.com/watch?v=mdh9GLWXWyY&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=14)
How to create extention points for a library

### [Exceptionally Bad: The Misuse of Exceptions in C++ & How to Do Better - Peter Muldoon](https://www.youtube.com/watch?v=Oy-VTqz1_58&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=27&pp=iAQB)
Talk about exceptions when and when not to use them

### [std::linalg: Linear Algebra Coming to Standard C++ - Mark Hoemmen](https://www.youtube.com/watch?v=-UXHMlAMXNk&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=37)
Improvement to livear algebra in c++

### [Great C++ is_trivial: trivial type traits - Jason Turner](https://www.youtube.com/watch?v=bpF1LKQBgBQ&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=109&pp=iAQB)
Make trivial class to improve quality and performance

### [Back to Basics: Debugging in Cpp - Greg Law](https://www.youtube.com/watch?v=qgszy9GquRs&list=PLHTh1InhhwT7gQEuYznhhvAYTel0qzl72&index=12)
Various tools to debug c++ and some compile time analysis

## 2022
### [Can C++ be 10x Simpler & Safer? - Herb Sutter](https://www.youtube.com/watch?v=ELeZAKCN4tY&list=PLHTh1InhhwT6c2JNtUiJkaH8YRqzhU7Ag&index=2&t=4840s)
Really interesting talk on a new syntaxe for c++, challenges and possibilities
### [Breaking Dependencies - The Visitor Design Pattern in Cpp - Klaus Iglberger](https://www.youtube.com/watch?v=PEcy1vYHb8A&list=PLHTh1InhhwT6c2JNtUiJkaH8YRqzhU7Ag&index=14)
Re-explaining visitor: use it when you want to add operations not type.

# CPP Now
## 2023
### [Value Oriented Programming Part 1: You Say You Want to Write a Function - Tony Van Eerd](https://www.youtube.com/watch?v=b4p_tcLYDV0&list=PL_AKIMJc4roUIwMsWnA9WPFJdCRfNUWHP&index=46)
General talk around code quality
### [Migration to Strong Types in C++: Interactive Tooling Support - Richárd Szalay -](https://www.youtube.com/watch?v=rcXf1VCA1Uc&list=PL_AKIMJc4roUIwMsWnA9WPFJdCRfNUWHP&index=20)
A clang tool to migrate to strong type. Essentially migrate from int to value type
### [Large Scale Automated Refactoring Across Translation Unit Boundaries in C++ - Zie Weaver](https://www.youtube.com/watch?v=1EMmgOKBWlI&list=PL_AKIMJc4roUIwMsWnA9WPFJdCRfNUWHP&index=15)
Clang tool and talk around AST produced by tools and how to make a parser and generator to refactor at large scale

# Code::Dive
## 2014
### [Scott Meyers: Cpu Caches and Why You Care](https://www.youtube.com/watch?v=WDIkqP4JbkE)
Hardware optimization is a thing and happen because of caches
Fetching a value for reading doesn't only fetch the value but the whole cache line (64 bytes)
Reading values from the same cache line is fast
Having to change cache line is costly: e.g. cache lien is full and new data is not in it
Arrays are the prefered data structure of cpu because contigus values can be read from the same cache line
For matix, row by row is faster than column by column (assuming columns are array of rows and rows array of values) for this reason
Writing a value invalidate the cache line, need to refetch it
False sharing occures when there is no logical dependency but hardware dependency. When multiple thread need to read/write (read only is not an issue) the same cache line. Better try to do a maximum of operation in the thread local storage and report to the global state only when necessary. Or copy the global state sub data set locally instead of trying to read it multiple times if there is a risque of it being invalidated.
