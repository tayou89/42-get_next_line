# Introduction
- This is one of [42 Seoul](https://42seoul.kr/en/seoul42/default.html) subjects.
- The purpose of this subject is to implement 'get_next_line' function.
- The function get file descriptor as input and return char *(usually string).
- Literally, read next line pointed by file descriptoro.
- function prototype: `char *get_next_line(int fd)`
- This is implemented adhering to the requirements, [Subject PDF](requirements/get_next_line.pdf) and [Norminette](requirements/nominette.pdf).
# Usage
- To use 'get_next_line', compile source code together.
- Include header file in the C file which needs to call 'get_next_line' function.
- Use the function with file descriptor and get returns of it.
# Required Knowledges for Implementation
- static variable
- file descriptor
- management of heap memory
- pointer