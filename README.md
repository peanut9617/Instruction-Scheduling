# Instruction-Scheduling

實作Tomasulo algorithm

programming language : python


Code to simulate Tomasulo’s - computer architecture hardware - algorithm for dynamic scheduling of instructions that allows out-of-order execution and enables more efficient use of multiple execution units.

  
set cycle:

    ADD 2 cycle
    MUL 10 cycle
    DIV 20 cycle


Input:

    ADDI F1, F2, 1
    SUB F1, F3, F4
    DIV F1, F2, F3
    MUL F2, F3, F4
    ADD F2, F4, F2
    ADDI F4, F1, 2
    MUL F5, F5, F5
    ADD F1, F4, F4
    

