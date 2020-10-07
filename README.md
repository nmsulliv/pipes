# Pipes

## Communication between Parent and Child Process via a Pipe
The program in pipes_processes1.c uses a 2-way pipe, to pass the string from
process 1 (P1) to process 2 (P2) and concatenates “howard.edu” and prints to the
stdout. Then P2 prompts user for a second input and passes the string to P1, and P1 
concatenates “gobison.org” to the string before printing it to stdout.

## Chaining Processes together using two Pipes
The program in pipes_processes3.c takes one argument from the command line using
argc and argv that is the argument passed to the grep program (e.g. Lakers or 28),
then three processes are created P1 (Parent - executes cat scores) and P2 
(Child - execute grep <your argument>) and P2 (Child’s Child - execute sort). 
The output of cat scores would be the input to grep Lakers, and int output from
grep Lakers would be the input for sort.

Example: cat scores | grep 28 | sort
Input
$./pipes_processes3 28
Output
Houston 44 28 .611
Indiana 45 28 .616
Oklahoma City 44 28 .611
Utah 44 28 .611