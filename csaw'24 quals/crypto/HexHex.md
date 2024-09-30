# HexHex
# Category
Crypto
# Description
Hexhex, Yes that's it! hehe
# Files
chall.txt
# Solution
First of all, most of the characters seem to be in hex, so we can just put that in a decoder. However, the decoded message is just a story about something irrelevant, and there are two lines that are still gibberish, seemingly whenever a weapon is mentioned in the story. 

It turns out, there's something called a twin-hex cipher, and once you know about it, we can just put the still encrypted lines in some online twin-hex decoder. In hindsight, the title of the challenge makes it pretty obvious, but it's hard to know if you haven't seem a twin-hex cipher before. Once you put in the two lines, the resultin messages are 'flag{fake_flag_heheheheheheh}' and 'csawctf{hex3d_i7_w3l7_innit_hehe}'.

Therefore, we know the flag is csawctf{hex3d_i7_w3l7_innit_hehe}.