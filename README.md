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
    


step 1:Set parameter

Register value:F1,F2,F3,F4,F5 可以給初始值

step 2:Read input file

step 3.Create Table

step 4:updateRS() updateRAT()

根據issue table進行issue的動作且印出所有table,如issue成功則將RS及RAT update,每回合只能執行一次

step 5:

判斷Buffer是否有在使用,如無使用可將RAT抓取下來並update Buffer

但currentCycle必須>Issue time,如抓取進去一樣印出所有table

step 6:

根據addcycle mulcycle divcycle判斷buffer計算是否結束

如結束就writeresult() 

並將RAT,RS,Register值進行update

step 7:重複執行step4~6

根據keepgoing及initialstate判斷是否繼續

initialstate初值為1,進行第一輪之後會設為0

keepgoint()則是判斷RAT,Buffer是否為空,如都為空則回傳0



output :

    ------------------------------Cycle 1------------------------------
    -----Register-----
    F1 1
    F2 1
    F3 2
    F4 None
    F5 None
    -----RAT-----
    F1 None
    F2 None
    F3 RS1
    F4 None
    F5 None
    -------RS-------
    RS1 + 1 2
    RS2 None None None
    RS3 None None None
    (ADD)Buffer=Empty
    RS4 None None None
    RS5 None None None
    (MUL)Buffer=Empty

    ------------------------------Cycle 2------------------------------
    -----Register-----
    F1 1
    F2 1
    F3 2
    F4 None
    F5 None
    -----RAT-----
    F1 None
    F2 None
    F3 RS1
    F4 RS4
    F5 None
    -------RS-------
    RS1 + 1 2
    RS2 None None None
    RS3 None None None
    (ADD)Buffer RS1=1+2
    RS4 / 1 RS1
    RS5 None None None
    (MUL)Buffer=Empty
