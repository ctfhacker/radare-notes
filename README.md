# radare2 notes
## String xref:

```
aa
s str.<TAB>
[0x08048a97]> s str.STOP__To_get_past_me_you_must_guess_the_number_I_am_thinking_of._n_nYou_may_guess_three_times._n_ 
[0x08049026]> axt
d 0x8048a97 push str.STOP__To_get_past_me_you_must_guess_the_number_I_am_thinking_of._n_nYou_may_guess_three_times._n_
[0x08049026]> s 0x8048a97
[0x08048a97]> pdf
/ (fcn) sub.write_a7e 48
|          0x08048a7e    55           push ebp
|          0x08048a7f    89e5         mov ebp, esp
|          0x08048a81    56           push esi
|          0x08048a82    53           push ebx
|          0x08048a83    83ec20       sub esp, 0x20
|          0x08048a86    8b5d08       mov ebx, dword [ebp + 8]         ; [0x8:4]=0
|          0x08048a89    e8c2fdffff   call sym.imp.rand
|             sym.imp.rand(unk, unk, unk)
|          0x08048a8e    8d75e0       lea esi, dword [ebp - 0x20]
|          0x08048a91    8945f0       mov dword [ebp - 0x10], eax
|          0x08048a94    50           push eax
|          0x08048a95    6a5f         push 0x5f                        ; '_'
|          0x08048a97    6826900408   push str.STOP__To_get_past_me_you_must_guess_the_number_I_am_thinking_of._n_nYou_may_guess_three_times._n_ ; "STOP! To get past me you must guess the number I am thinking of" @ 0x8049026
|          0x08048a9c    53           push ebx
|          0x08048a9d    e86efdffff   call sym.imp.write
|             sym.imp.write(unk, unk, unk, unk)
|          0x08048aa2    83c410       add esp, 0x10
|          0x08048aa5    c745dc00000. mov dword [ebp - 0x24], 0
\          0x08048aac    eb72         jmp fcn.08048b20
```
