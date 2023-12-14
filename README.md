# Stacks, Queues - LIFO, FIFO

## Description

Project 0x19. C - Stacks, Queues - LIFO, FIFO
An interpreter for Monty ByteCode files.

## Installing

```bash
git clone https://github.com/abbeycity500/monty.git
```

```bash
$ gcc -Wall -Werror -Wextra -pedantic *.c -o monty
```

## Usage

First make a file with Monty ByteCode commands
```bash
$ cat test.m
push 2
push 5
push 9
pall
```

Now run our interpreter with that file
```bash
$ ./monty test.m
9
5
2
```
## Examples

pint:
```bash
push 1
push 3
push 4
pint
```
Output will be:
4

pop:
```bash
push 1
push 2
push 3
pop
pall
```
Output will be:
2
1

swap:
```bash
push 1
push 2
push 3
swap
pall
```
Output will be:
2
3
1

## File Structure

0. [main.c](main.c) - The main function for monty interpreter.
* ``int main(int argc, char *argv[])`` - main function where program starts.
* ``buf_struct *make_struct(char *argv[])`` - make struct for buffers.

1. [dll_ops.c](dll_ops.c) - Doubly linked list operations.
* ``void free_stack(stack_t *head)`` - free list.

2. [exec_ops0.c](exec_ops0.c) - file where commands get executed.
* ``void exec_loop(buf_struct *a)`` - loop through commands and execute.
* ``void (*get_op_func(char *s))(stack_t **stack, unsigned int line_number)`` - calls function.

3. [helper_ops0.c](helper_ops0.c) - extra helper functions.
* ``int digits_only(char *str)`` - checks if push option is a number.

4. [op_code0.c](op_code0.c) - file for opcode basic commands.
* ``stack_t *push(stack_t **head, int n)`` - pushes node to top of stack.
* ``void pall(stack_t **stack, unsigned int line_n)`` - prints from the top of stack.
* ``void pint(stack_t **stack, unsigned int line_n)`` - print only top of stack.
* ``void pop(stack_t **stack, unsigned int line_n)`` - frees top of stack.
* ``void swap(stack_t **stack, unsigned int line_n)`` - swap first two nodes.

4. [op_code1.c](op_code1.c) - file for opcode math commands.
* ``void add(stack_t **stack, unsigned int line_n)`` - add top two elements of stack.
* ``void sub(stack_t **stack, unsigned int line_n)`` - subtracts top two elements of stack.
* ``void _div(stack_t **stack, unsigned int line_n)`` - divide top two elements.
* ``void mod(stack_t **stack, unsigned int line_n)`` - modulus top two elements.
* ``void mul(stack_t **stack, unsigned int line_n)`` - multiplies top two elements.

4. [op_code2.c](op_code2.c) - file for extra opcode commands.
* ``void nop(stack_t **stack, unsigned int line_n)`` - does nothing.
* ``void pchar(stack_t **stack, unsigned int line_n)`` - prints ascii character from head.
* ``void pstr(stack_t **stack, unsigned int line_n)`` - prints string.

5. [op_code3.c](op_code3.c) - file for extra opcode commands.
* ``void rotl(stack_t **stack, unsigned int line_n)`` - rotate list.
* ``void rotr(stack_t **stack, unsigned int line_n)`` - rotate list.
* ``void queue(stack_t **stack, unsigned int line_n)`` - flips list.

6. [split.c](split.c) - file for tokenizing lines from file.
* ``char **split_newline(buf_struct *a)`` - splits line based on newlines.
* ``char **split_spaces(char *buff, buf_struct *a)`` - splits line based on spaces and tabs.

# Monty
Monty is a Monty byte-code interpreter.

## Prerequisites
* Allowed editors: vi, vim, emacs
* All files will be compiled on Ubuntu 14.04 LTS
* Programs and functions will be compiled with gcc 4.8.4 using the flags -Wall -Werror -Wextra and -pedantic
* All files should end with a new line
* A README.md file, at the root of the folder of the project is mandatory
* The code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
* Allowed to use a maximum of one global variable
* No more than 5 functions per file
* Allowed to use the C standard library
* The prototypes of all your functions should be included in the header file called monty.h
* All the header files should be include guarded
* The repository monty should be added as a submodule to your holbertonschool-low_level_programming repository, under the name


## Available Opcodes
| Opcodes	| Description	|
| :-------:	| -----------	|
| push		| pushes an element to the stack |
| pall		| prints all the values in the stack |
| pint		| prints the value at the top of the stack |
| pop		| which removes the top element of the stack |
| swap		| swaps the top two elements of the stack |
| add		| adds the top two elements of the stack |
| nop		| doesn't do anything |
| sub		| subtracts the top element of the stack from the second top element |
| div		| divides the second top element of the stack by the top element |
| mul		| multiplies the second top element of the stack with the top element|
| mod		| mods the second top element of the stack with the top element |
| #		| treats the line as a comment |
| pchar		| prints the char at the top of the stack |
| pstr		| prints the string starting at the top of the stack |
| rotl		| rotates the stack to the top |
| rotr		| rotates the stack to the bottom |
| stack		| sets the format of the data to a stack (LIFO) |
| queue		| sets the format of the data to a queue (FIFO) |

## Brainf*ck
The `bf` folder contains the following Brainf*ck scripts

| BF Scripts	| Description	|
| :-------:	| -----------	|
| 1000-holberton.bf	| prints Holberton |
| 1001-add.bf		| reads two digits from stdin, add them, and print the result(one-digit) |
| 1002-mul.bf		| reads two digits from stdin, multiply them, and print the result (one-digit) |
| 1003-mul.bf		| reads two digits from stdin, multiply them, and print the result, followed by a new line |

### Installation
`$ sudo apt-get install bf`

### Usage
`$ bf <file_path>`

## Authors
* [Arowolo Wahab](https://github.com/abbeycity500)
* [Akinola Israel](https://github.com/hakinz0110)
