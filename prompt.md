# CXL fuzzing syzlang

The goal is to generate syz description that allows fuzzing CXL domain.

Syzlang description is in docs/syscall_descriptions_syntax.md

There are two hints.

1. libcxl directory contains user level cxl library
2. tr1 and tr2 are strace logs for valid CXL APIs.

Since CXL interface is openat() and write(), you need to write a syz description with '$' mark.

For example, 

openat$cxl_aa(...)
write$cxl_bb(...)

Output should be a single .txt file.