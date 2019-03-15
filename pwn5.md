# TAMUCTF - Pwn5 Challenge

Challenge found at: `nc pwn.tamuctf.com 4325`

### Who needs to do return-oriented programing when you have command injection?
I solved a Pwn problem using command injection when return oriented programming really should have been used.  This was done in a previous challenge, Pwn4 in this same CTF which can be accessed at `nc pwn.tamuctf.com 4324`.  In Pwn4, a simple command injection of ;cat flag.txt was used by many.  Pwn4 was easy because users could input any number of characters.  In Pwn5 however, the user can only input three characters.  If I tried to do `;cat flag.txt` again, the result would be `ls ;ca`.  Thus, I needed a way to do command injection while only using three characters.
<br>
Sure enough, there was a way to use command injection to get this flag as well.  As I considered what commands I could inject with only two characters, (since the semicolon already uses one character) the only command I could think of was vi.  Then, I remembered how powerful and broken vim is.  Turns out, if you type `:sh` into vim, it will give you a shell.  Thus, I typed `;vi` and I quickly had my shell.  From there I could call `cat flag.txt` and do anything else with the privilege of the vim program.
