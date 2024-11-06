# transposition-trial
# Category
Cryptography
# Description
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.
# Files
[message.txt](message.txt)
# Hints
1. Split the message up into blocks of 3 and see how the first block is scrambled
# Solution
Opening up the text file, I see that the message is `heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2`. Since the problem says every group of three is scrambled, and the first word is three letters, I can tell that the phrase should be `The flag is picoCTF{}`. Now I know the pattern of the scramble, which is just the first letter going to the end. Applying this pattern to every group of letters, I can finally get the flag.

Now I know that the flag is `picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}`.