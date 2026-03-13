Assignment 5
---
# Team Members:
- Zach Callahan
- Justin Liang

# Expected Data Structures
A coverage tester likely works by iterating through the list of test functions, calling the program line-by-line and recording which lines are called. This would require either a map or set to keep track of called lines (depending on whether the program remembers which tests call which line), and a qeueue or priority qeueue to manage the function calls. A more advanced tester might employ a stack to keep track of the program's call stack, but that isn't in the implementation requirements.


# Initial Code Examination
This project is fairly well organized. While not much is detailed in the readme, it links to an external site that contains documentation and use cases. Additionally, the source code is structured, encapsulated, and annotated. 

Most of the files are peripheral and handle edge issues like plugins and exceptions. The bulk of the program is focused on parsing and program control/specification (i.e. deciding the most efficient method to use). The project also contains html files for cover style, a multitude of tests, and bytecode for command line usage.

### Tests:
- test_core.py: Tests that the coverage core is correctly chosen (I believe the core refers to the method of coverage employed?)
- test_phystokens.py: Tests that the program's included text tokenizer works correctly.

### Program Files:
- data.py: This takes several coverage data files (presumably the program it is being run on) and amalgamates it into a mapping of the coverage.
- collector.py: This uses threading to create "tracers", each of which moves through the program execution and finds the lines covered by each function. It appears to be the main data collection file.
- multiproc.py: A bit above my pay grade; it appears to alter the runtime code of the program to allow multiprocessing. Not sure why.
- tracer.pyi: Looks to be a wrapper for tracer.c
- cmdline.py: Full command-line support, including arguments and a help exception.


# Detailed Code Examination
Judging by earlier examinations, the data.py file seems to make use of a map implemented via a hash table. As previously mentioned, it contains functions that take in data files and "CoverageData" dataclasses, performing operations like combining and tracking. While there are no included data structures, multiple operations like hash\_for\_data\_file and add\_data\_to\_hash reference external hashes and hashing algorithms. The functions in this file are closely connected to the overarching idea of hashing as a method to track the call traces throughout the inputted program.

# Summary
Placeholder text.
