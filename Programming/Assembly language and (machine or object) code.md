An assembly language is a processor-specific language that uses mnemonic abbreviations to define low-level machine instructions. The mnemonic abbreviations are translated into machine code (also called object code) by an [[assembler]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#assembler).

The abbreviations usually consist of the name for the instruction followed by operands which are register names such as 'sp' ([[stack]] pointer) and 'a0' (address register 0), memory references such as 'A' (local label) and 'putint' ([[function]] label), and memory offsets such as '20(sp)' (20 bytes/words from the location pointed to be the [[stack]] pointer).

Example MIPS assembly program to compute GCD (from textbook page 1):

   addiu    sp,sp,-32
   sw       ra,20(sp)
   jal      getint
   nop
   jal      getint
   sw       v0,28(sp)
   lw       a0,28(sp)
   move     v1,v0
   beq      a0,v0,D
   slt      at,v1,a0
A: beq      at,zero,B
   nop
   b        C
   subu     a0,a0,v1
B: subu     v1,v1,a0
C: bne      a0,v1,A
   slt      at,v1,a0
D: jal      putint
   nop
   lw       ra,20(sp)
   addiu    sp,sp,32
   jr       ra
   move     v0,zero

Example MIPS R4000 machine code of the above assembly program (from textbook page 1):

27bdffd0 afbf0014 0c1002a8 00000000 0c1002a8 afa2001c 8fa4001c
00401825 10820008 0064082a 10200003 00000000 10000002 00832023
00641823 1483fffa 0064082a 0c1002b2 00000000 8fbf0014 27bd0020
03e00008 00001025