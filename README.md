# Instruction-Scheduling

實作Tomasulo algorithm

programming language : python


Code to simulate Tomasulo’s - computer architecture hardware - algorithm for dynamic scheduling of instructions that allows out-of-order execution and enables more efficient use of multiple execution units.

  
set cycle:

    ADD 2 cycle
    SUB 2 cycle
    MUL 10 cycle
    DIV 20 cycle


Input:

    SUB F1, F3, F4
    DIV F1, F2, F3
    MUL F2, F3, F4
    ADD F2, F4, F2
    MUL F5, F5, F5
    ADD F1, F4, F4
    


1.Set parameter:
Register value:F1,F2,F3,F4,F5 可給初值

2.Read input file:

3.Create Table:
Issue table: 根據input file create issue list

4.updateRS() updateRAT()根據issue table進行issue的動作且印出所有table,如issue成功則將RS及RAT update,每回合只能執行一次

5.判斷Buffer是否有在使用,如無使用可將RAT抓取下來並update Buffer,但currentCycle必須>Issue time,如抓取進去一樣印出所有table

6.根據addcycle mulcycle divcycle判斷buffer計算是否結束,如結束writeresult() 會將RAT,RS,Register值進行update

7.Loop step4~6,根據keepgoing及initialstate判斷是否繼續,initialstate初值為1,進行第一輪之後會設為0,keepgoint()則是判斷RAT,Buffer是否為空,如都為空則回傳0
