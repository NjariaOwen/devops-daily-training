/proc files i think they provide real-time system and process information

then the comand uname it displays the information about the system when we used the
flag -a it displays all info about my system while the -r shows the kernel release

when the cat the cpuinfo i can see alot of data about the system mostly the cpu
itself like the processor the vendor id of the processor the model of the cpu and 
many more info i will know about as time goes by i saw even there is speed 

the mem info shows the total mem space thats there the free mem space like all
about memory usage but one thing i noticed is it is all in kB

uname -a                                                                 git:main*
Linux NOD3-N3MO 6.17.0-20-generic #20~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Mar 19 01:28:37 UTC 2 x86_64 x86_64 x86_64 GNU/Linux

~ ➤ uname -r                                                                 git:main*
6.17.0-20-generic

what is PID 1? pid in full is process id so when we enter the proc dir it shows the
pid 1 is systemd and it shows the state as s(sleeping) even if it is sleeping it
seems to be a very impotant process the system needs thats why it hasnt given away
that id to another process so if that process is killed it means the system may
have issues


when i run ls /proc/1/fd i think it shows all other proceses that rely on the that
one process PID 1 am not sure if am wrong tell me but i thought it that way because of:

sudo ls /proc/1/fd                                                       git:main*
[sudo] password for owen: 
0    119  137  163  196  21   233  249	263  278  292  307  324  348  4    53  71  86
1    12   14   164  197  210  234  25	264  279  293  308  325  35   40   55  72  87
10   120  144  165  198  211  235  250	265  28   295  309  326  36   41   56  73  88
100  121  146  166  199  213  236  251	266  280  296  31   327  37   42   57  74  89
102  122  147  167  2	 214  237  252	267  281  297  310  328  375  43   58  75  9
105  123  148  168  20	 22   238  253	268  282  298  312  329  376  44   6   76  90
108  124  149  169  200  222  239  254	269  283  299  313  33	 38   45   62  77  91
11   126  15   17   201  223  240  255	27   284  3    314  330  381  46   63  78  92
111  129  150  172  202  224  241  256	270  285  30   315  331  382  47   64  79  93
112  13   152  18   203  226  242  257	271  286  300  316  332  383  48   65  8   94
113  130  153  182  204  227  243  258	272  287  301  317  335  384  49   66  80  95
114  131  154  19   205  228  244  259	273  288  302  318  336  388  495  67  81  96
115  132  155  192  206  23   245  26	274  289  303  32   338  39   5    68  82  97
116  133  156  193  207  230  246  260	275  29   304  320  339  390  50   69  83  98
117  135  159  194  208  231  247  261	276  290  305  321  34	 391  51   7   84  99
118  136  16   195  209  232  248  262	277  291  306  322  347  393  52   70  85
~ ➤         
