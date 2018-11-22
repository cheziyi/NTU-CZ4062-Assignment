Source: http://ftp.gnu.org/gnu/binutils/binutils-2.15.tar.bz2



Input: `out_20181119_22_32_01/crash/w01_000000,sig:11,Havoc:5594:27520,src:w01_000115`
A null pointer dereference bug was found in function work_stuff_copy_to_from()(cplus-dem.c:1208)
```
Program received signal SIGSEGV, Segmentation fault.
strlen () at ../sysdeps/x86_64/strlen.S:106
106     ../sysdeps/x86_64/strlen.S: No such file or directory.
```
```
#0  strlen () at ../sysdeps/x86_64/strlen.S:106
#1  0x00000000004f1f7c in work_stuff_copy_to_from (to=0x7fffffffe430, from=0x7fffffffe570)
    at ../../libiberty/cplus-dem.c:1208
#2  0x00000000004ef73c in iterate_demangle_function (work=0x7fffffffe570, mangled=<optimized out>,
    declp=0x7fffffffe4f0, scan=0x7339c5 <mbuffer+5> "__p__.") at ../../libiberty/cplus-dem.c:2625
#3  0x00000000004dbc65 in internal_cplus_demangle (work=0x7fffffffe570, mangled=<optimized out>)
    at ../../libiberty/cplus-dem.c:2865
#4  0x00000000004dab41 in cplus_demangle (mangled=0x7339c0 <mbuffer> "_Q_____p__.", options=<optimized out>)
    at ../../libiberty/cplus-dem.c:936
#5  0x00000000004027b9 in main (argc=<optimized out>, argv=<optimized out>) at ../../binutils/cxxfilt.c:270
```
```
(gdb) p from
$36 = (struct work_stuff *) 0x7fffffffe570
(gdb) p from->btypevec
$37 = (char **) 0x75d430
(gdb) p from->numb
$38 = 1
(gdb) p from->btypevec[0]
$39 = 0x0
(gdb) p *from->btypevec[0]
Cannot access memory at address 0x0
```
libiberty/cplus-dem.c
```
1206  for (i = 0; i < from->numb; i++)
1207    {
1208      int len = strlen (from->btypevec[i]) + 1;
1209
1210      to->btypevec[i] = xmalloc (len);
1211      memcpy (to->btypevec[i], from->btypevec[i], len);
1212    }
```



Input: `out_20181119_22_32_01/crash/w01_000001,sig:11,Havoc:5470:31360,src:w01_000129`
A null pointer dereference bug was found in function cplus_demangle_type()(cp-demangle.c:1827)
```
Program received signal SIGSEGV, Segmentation fault.
cplus_demangle_type (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1827
1827    ../../libiberty/cp-demangle.c: No such file or directory.
```
```
#0  cplus_demangle_type (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1827
#1  0x0000000000501e7b in d_bare_function_type (di=0x7fffffffe4b8, has_return_type=0)
    at ../../libiberty/cp-demangle.c:2041
#2  0x00000000004f4b4a in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1091
#3  0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#4  d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#5  0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#6  0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#7  d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#8  0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#9  0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#10 d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#11 0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#12 0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#13 d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#14 0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=1) at ../../libiberty/cp-demangle.c:1056
#15 0x000000000050026a in cplus_demangle_mangled_name (top_level=1, di=<optimized out>)
    at ../../libiberty/cp-demangle.c:980
#16 d_demangle (mangled=0x7339c0 <mbuffer> "_ZZZZZZdd", options=267, palc=0x7fffffffe550)
    at ../../libiberty/cp-demangle.c:3853
#17 0x000000000050001c in cplus_demangle_v3 (mangled=0x12 <error: Cannot access memory at address 0x12>,
    options=7649760) at ../../libiberty/cp-demangle.c:4011
#18 0x00000000004daa6c in cplus_demangle (mangled=0x7339c0 <mbuffer> "_ZZZZZZdd", options=<optimized out>)
    at ../../libiberty/cplus-dem.c:921
#19 0x00000000004027b9 in main (argc=<optimized out>, argv=<optimized out>) at ../../binutils/cxxfilt.c:270
```
```
(gdb) p ret
$1 = (struct demangle_component *) 0x0
(gdb) p ret->u.s_builtin.type
Cannot access memory at address 0x8
```
libiberty/cp-demangle.c
```
1819  switch (peek)
1820    {
1821    case 'a': case 'b': case 'c': case 'd': case 'e': case 'f': case 'g':
1822    case 'h': case 'i': case 'j':           case 'l': case 'm': case 'n':
1823    case 'o':                               case 's': case 't':
1824    case 'v': case 'w': case 'x': case 'y': case 'z':
1825      ret = d_make_builtin_type (di,
1826				 &cplus_demangle_builtin_types[peek - 'a']);
1827      di->expansion += ret->u.s_builtin.type->len;
1828      can_subst = 0;
1829      d_advance (di, 1);
1830      break;
```



Input: `out_20181119_22_32_01/crash/w01_000015,sig:11,Havoc:1323:30080,src:w01_000270`
A null pointer dereference bug was found in function d_name()(cp-demangle.c:1167)
```
Program received signal SIGSEGV, Segmentation fault.
0x0000000000500ff7 in d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1167
1167    ../../libiberty/cp-demangle.c: No such file or directory.
```
```
#0  0x0000000000500ff7 in d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1167
#1  0x00000000004f62a3 in d_class_enum_type (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2082
#2  cplus_demangle_type (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1846
#3  0x0000000000501e7b in d_bare_function_type (di=0x7fffffffe4b8, has_return_type=0)
    at ../../libiberty/cp-demangle.c:2041
#4  0x00000000004f4b4a in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1091
#5  0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#6  d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#7  0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#8  0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#9  d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#10 0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#11 0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#12 d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#13 0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#14 0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#15 d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#16 0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#17 0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#18 d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#19 0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=1) at ../../libiberty/cp-demangle.c:1056
#20 0x000000000050026a in cplus_demangle_mangled_name (top_level=1, di=<optimized out>)
    at ../../libiberty/cp-demangle.c:980
#21 d_demangle (mangled=0x7339c0 <mbuffer> "_ZZZZZZZ", options=267, palc=0x7fffffffe550)
    at ../../libiberty/cp-demangle.c:3853
#22 0x000000000050001c in cplus_demangle_v3 (mangled=0x7fffffffe4b8 "\300\071s", options=-7376)
    at ../../libiberty/cp-demangle.c:4011
#23 0x00000000004daa6c in cplus_demangle (mangled=0x7339c0 <mbuffer> "_ZZZZZZZ", options=<optimized out>)
    at ../../libiberty/cplus-dem.c:921
#24 0x00000000004027b9 in main (argc=<optimized out>, argv=<optimized out>) at ../../binutils/cxxfilt.c:270
```
```
(gdb) p peek
$2 = <optimized out>
(gdb) p di
$3 = (struct d_info *) 0x7fffffffe4b8
```
libiberty/cp-demangle.c
```
1111  char peek = d_peek_char (di);
1112  struct demangle_component *dc;
1113
1114  switch (peek)
1115    {
...
1165    default:
1166      dc = d_unqualified_name (di);
1167      if (d_peek_char (di) == 'I')
```


Input: `out_20181119_22_32_01/crash/w01_000200,sig:11,Havoc:287:368,src:w01_001883`
A null pointer dereference bug was found in function do_type()(cplus-dem.c:3760)
```
Program received signal SIGSEGV, Segmentation fault.
0x00000000004d5e8a in do_type (work=0x7fffffffe570, mangled=0x7fffffffe4e8, result=0x7fffffffe340)
    at ../../libiberty/cplus-dem.c:3760
3760    ../../libiberty/cplus-dem.c: No such file or directory.
```
```
#0  0x00000000004d5e8a in do_type (work=0x7fffffffe570, mangled=0x7fffffffe4e8, result=0x7fffffffe340)
    at ../../libiberty/cplus-dem.c:3760
#1  0x00000000004dfe9a in demangle_signature (work=0x7fffffffe570, mangled=0x7fffffffe4e8, declp=0x7fffffffe4f0)
    at ../../libiberty/cplus-dem.c:1436
#2  0x00000000004ef7d0 in iterate_demangle_function (work=0x7fffffffe570, mangled=<optimized out>,
    declp=0x7fffffffe4f0, scan=0x7339c4 <mbuffer+4> "__B3333333333_s") at ../../libiberty/cplus-dem.c:2636
#3  0x00000000004dbc65 in internal_cplus_demangle (work=0x7fffffffe570, mangled=<optimized out>)
    at ../../libiberty/cplus-dem.c:2865
#4  0x00000000004dab41 in cplus_demangle (mangled=0x7339c0 <mbuffer> "a__m__B3333333333_s", options=<optimized out>)
    at ../../libiberty/cplus-dem.c:936
#5  0x00000000004027b9 in main (argc=<optimized out>, argv=<optimized out>) at ../../binutils/cxxfilt.c:270
```
```
(gdb) p work
$6 = (struct work_stuff *) 0x7fffffffe570
(gdb) p work->btypevec
$7 = (char **) 0x0
```
libiberty/cplus-dem.c
```
3754    /* A back reference to a previously seen squangled type */
3755    case 'B':
3756      (*mangled)++;
3757      if (!get_count (mangled, &n) || n >= work -> numb)
3758	success = 0;
3759      else
3760	string_append (result, work->btypevec[n]);
3761      break;
```



Input: `out_20181119_22_32_01/crash/w01_000400,sig:11,Havoc:182:532,src:w01_003608`
A stack overflow / null pointer dereference bug was found in function d_substitution()(cp-demangle.c:2589)
```
Program received signal SIGSEGV, Segmentation fault.
0x00000000004f830b in d_substitution (di=0x7fffffffe4b8, prefix=<optimized out>) at ../../libiberty/cp-demangle.c:2589
2589    in ../../libiberty/cp-demangle.c
```
```
#0  0x00000000004f830b in d_substitution (di=0x7fffffffe4b8, prefix=<optimized out>) at ../../libiberty/cp-demangle.c:2589
#1  0x000000000050134d in d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1128
#2  0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=0) at ../../libiberty/cp-demangle.c:1056
#3  0x0000000000500d82 in d_local_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:2446
#4  d_name (di=0x7fffffffe4b8) at ../../libiberty/cp-demangle.c:1120
#5  0x00000000004f46ee in d_encoding (di=0x7fffffffe4b8, top_level=1) at ../../libiberty/cp-demangle.c:1056
#6  0x000000000050026a in cplus_demangle_mangled_name (top_level=1, di=<optimized out>) at ../../libiberty/cp-demangle.c:980
#7  d_demangle (mangled=0x7339c0 <mbuffer> "_ZZS", 'Z' <repeats 13 times>, "MZZZZZZZGZZZ_S__________O____", options=267, palc=0x7fffffffe550) at ../../libiberty/cp-demangle.c:3853
#8  0x000000000050001c in cplus_demangle_v3 (mangled=0x7fffffffe4b8 "\300\071s", options=-1364035264) at ../../libiberty/cp-demangle.c:4011
#9  0x00000000004daa6c in cplus_demangle (mangled=0x7339c0 <mbuffer> "_ZZS", 'Z' <repeats 13 times>, "MZZZZZZZGZZZ_S__________O____", options=<optimized out>)
    at ../../libiberty/cplus-dem.c:921
#10 0x00000000004027b9 in main (argc=<optimized out>, argv=<optimized out>) at ../../binutils/cxxfilt.c:270
```
```
(gdb) p di
$24 = (struct d_info *) 0x7fffffffe4b8
(gdb) p di->next_sub
$26 = 0
(gdb) p di->subs
$27 = (struct demangle_component **) 0x7fffffffdaa0
(gdb) p di->subs[0]
$30 = (struct demangle_component *) 0x7fffffffe4b8
```
libiberty/cp-demangle.c
```
2562  if (c == '_' || IS_DIGIT (c) || IS_UPPER (c))
2563    {
2564      int id;
2565
2566      id = 0;
...
2584      if (id >= di->next_sub)
2585	return NULL;
2587      ++di->did_subs;
2588
2589      return di->subs[id];
2590    }
```