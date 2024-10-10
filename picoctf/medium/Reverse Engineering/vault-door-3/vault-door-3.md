# vault-door-3
# Category
Reverse Engineering
# Description
This vault uses for-loops and byte arrays.
# Files
[VaultDoor3.java](VaultDoor3.java)
# Hints
1. Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.
# Solution
After looking at the code, we can see that the door checks the password to this string: `jU5t_a_sna_3lpm18gb41_u_4_mfr340` after performing some operations to the input. We can split this up into four parts:

Part 1:
```
for (i=0; i<8; i++) {
    buffer[i] = password.charAt(i);
}
```
Since we can see that nothing is changed, we know that the first part of the password is `jU5t_a_s`.

Part 2:
```
for (; i<16; i++) {
    buffer[i] = password.charAt(23-i);
}
```
Since `i` ended at 8, we can see that it takes the reverse of the 8 character string. Since the next 8 characters of the buffer is `na_3lpm1`, we know that the second part of the password is `1mpl3_an`.

Part 3: 
```
for (; i<32; i+=2) {
    buffer[i] = password.charAt(46-i);
}
```
This is pretty much the same as part 2, except this increments by two everytime, skipping every other character on the way. Reversing the buffer for the selected characters, we know that the third part of the password is `4 r m 4 u 1 b 8`.

Part 4:
```
for (i=31; i>=17; i-=2) {
    buffer[i] = password.charAt(i);
}
```
For the last part, the loop is decreasing, and is decrementing by two, which can just be treated like an increasing loop with an increment of 2. Following the logic, we know that the fourth part of the password is `g 4 _ _ _ f 3 0`. Combining parts 3 and 4, we get that the last half of the flag is `4gr4m_4_u_1fb380`.

Combining all the parts together, we get that the password is `jU5t_a_s1mpl3_an4gr4m_4_u_1fb380`.

Now I know that the flag is `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}`.