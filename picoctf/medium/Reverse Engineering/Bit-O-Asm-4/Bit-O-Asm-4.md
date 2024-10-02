# Bit-O-Asm-4
# Category
Reverse Engineering
# Description
Can you figure out what is in the eax register? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
# Files
[disassembler-dump0_d.txt](disassembler-dump0_d.txt)
# Hints
1. Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.
2. Of course, if you're really good, you'll only need one attempt to solve this problem.
# Solution
Starting from the beginning, we see that rbp-0x4 is assigned to the value 0x9fe1a, and then compared to the value 0x2710. Obviously, they are different numbers, so the next line does nothing, since it only jumps if the two values being compared are equal. 0x65 is then subtracted from rbp-0x4, resulting in a value of 654874-101=654773. It then jumps to line 41, where eax is being initialized with the value of rbp-0x4, so the final value of eax is 654773.

Thus, the flag is picoCTF{654773}.