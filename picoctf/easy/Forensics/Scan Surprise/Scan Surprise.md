# Scan Surprise
# Category
Forensics
# Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
The same files are accessible via SSH here:
ssh -p 49628 ctf-player@atlas.picoctf.net
Using the password f3b61b38. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
# Files
None
# Hints
1. QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
2. Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
3. If you don't have access to a phone, you can also use zbar-tools to convert an image to text
# Solution
This is a pretty straightforward challenge, since I was immediately greeted with a QR code once I connected to the shell:

![alt text](image.png)

I used my phone to scan the QR code, and it directed me to a link that was the flag. Simple!

Now I know that the flag is picoCTF{p33k_@_b00_d4ca652e}.