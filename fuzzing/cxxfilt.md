Input: `out_20181119_22_32_01/crash/w01_000000,sig:11,Havoc:5594:27520,src:w01_000115`
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
(gdb)
```


Input: `out_20181119_22_32_01/crash/w01_000001,sig:11,Havoc:5470:31360,src:w01_000129`
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


Input: `out_20181119_22_32_01/crash/w01_000015,sig:11,Havoc:1323:30080,src:w01_000270`
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


Input: `out_20181119_22_32_01/crash/w01_000200,sig:11,Havoc:287:368,src:w01_001883`
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


Input: `out_20181119_22_32_01/crash/w01_000400,sig:11,Havoc:182:532,src:w01_003608`
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