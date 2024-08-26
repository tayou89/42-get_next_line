# get_next_line

## Description
This project involves creating a function called `get_next_line` that reads a line from a file descriptor. When called in a loop, the function should allow reading the text file pointed to by the file descriptor, one line at a time.

## Function Prototype
```c
char *get_next_line(int fd);
```

## Parameters
- `fd`: The file descriptor to read from

## Return Value
- Read line: correct behavior
- NULL: there is nothing else to read, or an error occurred

## Requirements
- The function should work as expected both when reading from a file and when reading from standard input.
- The returned line should include the terminating `\n` character, except if the end of file was reached and does not end with a `\n` character.
- The program must compile with the flag `-D BUFFER_SIZE=n`, which will be used as the buffer size for the read calls in your `get_next_line`.
- The program should compile with and without the `-D BUFFER_SIZE` flag.

## Compilation
```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 <files>.c
```

## Forbidden
- You are not allowed to use your libft in this project.
- The use of `lseek()` is forbidden.
- Global variables are forbidden.

## Bonus Part
- Develop `get_next_line()` using only one static variable.
- Your `get_next_line()` can manage multiple file descriptors simultaneously.

## Norminette
This project follows the Norm, which is the coding standard of 42 School. The code must pass the `norminette` check, which enforces these standards. For more information about the Norm, refer to the [norminette.pdf](requirements/nominette.pdf) file in the requirements directory.

## Project PDF
For detailed project requirements and guidelines, please refer to the [get_next_line.pdf](requirements/get_next_line.pdf) file in the requirements directory.

## Example Test Code
Here's a simple example of how to use the `get_next_line` function:

```c
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main()
{
    int fd;
    char *line;

    fd = open("test.txt", O_RDONLY);
    if (fd == -1)
    {
        printf("Error opening file\n");
        return (1);
    }

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }

    close(fd);
    return (0);
}
```

This test code opens a file named "test.txt", reads it line by line using `get_next_line`, prints each line, and then frees the memory. Remember to compile this with your `get_next_line` implementation.

Remember to thoroughly test your implementation with various buffer sizes and different types of input!