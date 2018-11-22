Input: `out_20181119_22_31_58/crash/w01_000000,sig:11,Havoc:6628:22272,src:w00_000014`
```
Program received signal SIGSEGV, Segmentation fault.
mjs_parse_ffi_signature (mjs=0x666010, s=0x0, sig_len=0, sig=0x666770, sig_type=FFI_SIG_FUNC) at mjs.c:8289
8289    mjs.c: No such file or directory.
```
```
#0  mjs_parse_ffi_signature (mjs=0x666010, s=0x0, sig_len=0, sig=0x666770, sig_type=FFI_SIG_FUNC) at mjs.c:8289
#1  0x000000000040d079 in mjs_ffi_call (mjs=0x666010) at mjs.c:8739
#2  0x0000000000417048 in mjs_execute (mjs=0x666010, off=145, res=0x7fffffffe4d8) at mjs.c:7902
#3  0x0000000000411a01 in mjs_exec_internal (mjs=0x666010, path=<optimized out>, src=<optimized out>,
    generate_jsc=<optimized out>, res=0x7fffffffe5b0) at mjs.c:8106
#4  0x000000000041d749 in mjs_exec_file (mjs=<optimized out>,
    path=0x7fffffffe8ea "out_20181119_22_31_58/crash/w01_000000,sig:11,Havoc:6628:22272,src:w00_000014",
    res=<optimized out>) at mjs.c:8129
#5  main (argc=<optimized out>, argv=0x7fffffffe6e8) at mjs.c:10302
```

Input: `out_20181119_22_31_58/crash/w01_000001,sig:6,Havoc:11108:24896,src:w00_000012`
```
mjs_main: mjs.c:10345: struct mjs_object *get_object_struct(mjs_val_t): Assertion `mjs_is_object(v)' failed.

Program received signal SIGABRT, Aborted.
0x00007ffff783e428 in __GI_raise (sig=sig@entry=6) at ../sysdeps/unix/sysv/linux/raise.c:54
54      ../sysdeps/unix/sysv/linux/raise.c: No such file or directory.
```
```
#0  0x00007ffff783e428 in __GI_raise (sig=sig@entry=6) at ../sysdeps/unix/sysv/linux/raise.c:54
#1  0x00007ffff784002a in __GI_abort () at abort.c:89
#2  0x00007ffff7836bd7 in __assert_fail_base (fmt=<optimized out>,
    assertion=assertion@entry=0x441520 "mjs_is_object(v)", file=file@entry=0x440194 "mjs.c", line=line@entry=10345,
    function=function@entry=0x441531 "struct mjs_object *get_object_struct(mjs_val_t)") at assert.c:92
#3  0x00007ffff7836c82 in __GI___assert_fail (assertion=0x441520 "mjs_is_object(v)", file=0x440194 "mjs.c",
    line=10345, function=0x441531 "struct mjs_object *get_object_struct(mjs_val_t)") at assert.c:101
#4  0x000000000041c0f6 in get_object_struct (v=<optimized out>) at mjs.c:10345
#5  mjs_get_own_property (obj=<optimized out>, name=<optimized out>, len=<optimized out>, mjs=<optimized out>)
    at mjs.c:10377
#6  mjs_get_own_property_v (mjs=<optimized out>, obj=<optimized out>, key=<optimized out>) at mjs.c:10403
#7  mjs_find_scope (mjs=<optimized out>, key=<optimized out>) at mjs.c:7196
#8  mjs_execute (mjs=<optimized out>, off=285, res=0x7fffffffe4d8) at mjs.c:7722
#9  0x0000000000411a01 in mjs_exec_internal (mjs=0x666010, path=<optimized out>, src=<optimized out>,
    generate_jsc=<optimized out>, res=0x7fffffffe5b0) at mjs.c:8106
#10 0x000000000041d749 in mjs_exec_file (mjs=<optimized out>,
    path=0x7fffffffe8ea "out_20181119_22_31_58/crash/w01_000001,sig:6,Havoc:11108:24896,src:w00_000012",
    res=<optimized out>) at mjs.c:8129
#11 main (argc=<optimized out>, argv=0x7fffffffe6e8) at mjs.c:10302
```

Input: `out_20181119_22_31_58/crash/w01_000008,sig:6,Havoc:58:5888,src:w00_000000`
```
mjs_main: mjs.c:7018: mjs_val_t mjs_pop_val(struct mbuf *): Assertion `m->len >= sizeof(v)' failed.

Program received signal SIGABRT, Aborted.
0x00007ffff783e428 in __GI_raise (sig=sig@entry=6) at ../sysdeps/unix/sysv/linux/raise.c:54
54      ../sysdeps/unix/sysv/linux/raise.c: No such file or directory.
```
```
#0  0x00007ffff783e428 in __GI_raise (sig=sig@entry=6) at ../sysdeps/unix/sysv/linux/raise.c:54
#1  0x00007ffff784002a in __GI_abort () at abort.c:89
#2  0x00007ffff7836bd7 in __assert_fail_base (fmt=<optimized out>,
    assertion=assertion@entry=0x4409c2 "m->len >= sizeof(v)", file=file@entry=0x440194 "mjs.c", line=line@entry=7018,
    function=function@entry=0x4409d6 "mjs_val_t mjs_pop_val(struct mbuf *)") at assert.c:92
#3  0x00007ffff7836c82 in __GI___assert_fail (assertion=0x4409c2 "m->len >= sizeof(v)", file=0x440194 "mjs.c",
    line=7018, function=0x4409d6 "mjs_val_t mjs_pop_val(struct mbuf *)") at assert.c:101
#4  0x000000000041c5e0 in mjs_pop_val (m=<optimized out>) at mjs.c:7018
#5  mjs_pop (mjs=<optimized out>) at mjs.c:7008
#6  exec_expr (op=<optimized out>, mjs=<optimized out>) at mjs.c:7329
#7  mjs_execute (mjs=<optimized out>, off=<optimized out>, res=<optimized out>) at mjs.c:7934
#8  0x0000000000411a01 in mjs_exec_internal (mjs=0x666010, path=<optimized out>, src=<optimized out>,
    generate_jsc=<optimized out>, res=0x7fffffffe5b0) at mjs.c:8106
#9  0x000000000041d749 in mjs_exec_file (mjs=<optimized out>,
    path=0x7fffffffe8ee "out_20181119_22_31_58/crash/w01_000008,sig:6,Havoc:58:5888,src:w00_000000",
    res=<optimized out>) at mjs.c:8129
#10 main (argc=<optimized out>, argv=0x7fffffffe6e8) at mjs.c:10302
```


Input: `out_20181119_22_31_58/crash/w01_000020,sig:11,Splice:69:573,src:w01_001293`
```
Program received signal SIGSEGV, Segmentation fault.
__memcpy_avx_unaligned () at ../sysdeps/x86_64/multiarch/memcpy-avx-unaligned.S:267
267     ../sysdeps/x86_64/multiarch/memcpy-avx-unaligned.S: No such file or directory.
```
```
#0  __memcpy_avx_unaligned () at ../sysdeps/x86_64/multiarch/memcpy-avx-unaligned.S:267
#1  0x000000000041fde5 in embed_string (m=<optimized out>, offset=<optimized out>, p=0x686fa5 "", flags=1 '\001',
    len=<optimized out>) at mjs.c:12208
#2  mjs_mk_string (mjs=<optimized out>, p=<optimized out>, len=18446744073709551614, copy=<optimized out>)
    at mjs.c:11789
#3  0x000000000043ca46 in frozen_cb (data=0x666c30,
    name=0x6668f2 "e\": \"\312\\\": {\"a\": 1, \"b", '=' <repeats 20 times>, "\": \"foo\", \"c\": true, \"d\": [null], \"e\": \"\312\\d2\"}", name_len=1, path=<optimized out>, token=0x7fffffffde08) at mjs.c:10104
#4  0x0000000000424e98 in parse_string (f=0x7fffffffe1b0) at mjs.c:5043
#5  0x000000000042355b in parse_value (f=0x7fffffffe1b0) at mjs.c:5129
#6  0x00000000004256f2 in parse_pair (f=0x7fffffffe1b0) at mjs.c:5195
#7  0x0000000000424575 in parse_object (f=<optimized out>) at mjs.c:5208
#8  parse_value (f=0x7fffffffe1b0) at mjs.c:5132
#9  0x00000000004256f2 in parse_pair (f=0x7fffffffe1b0) at mjs.c:5195
#10 0x0000000000424575 in parse_object (f=<optimized out>) at mjs.c:5208
#11 parse_value (f=0x7fffffffe1b0) at mjs.c:5132
#12 0x00000000004256f2 in parse_pair (f=0x7fffffffe1b0) at mjs.c:5195
#13 0x0000000000424575 in parse_object (f=<optimized out>) at mjs.c:5208
#14 parse_value (f=0x7fffffffe1b0) at mjs.c:5132
#15 0x0000000000407f6b in doit (f=<optimized out>) at mjs.c:5222
#16 json_walk (
    json_string=0x66689b "{\"a\": {\"a\": 1, \"ba\": {\"a\": 1, \"b", '=' <repeats 20 times>, "\": \"foo\", \"c\": true, \"d\": [null], \"e\": \"\312\\\": {\"a\": 1, \"b", '=' <repeats 20 times>, "\": \"foo\", \"c\": true, \"d\": [null], \"e\": \"\312\\d2\"}", json_string_length=6844325, callback=0xfffffffffffdfde9, callback_data=<optimized out>)
    at mjs.c:5578
#17 0x000000000040f036 in mjs_json_parse (mjs=<optimized out>, str=<optimized out>, len=<optimized out>,
    res=<optimized out>) at mjs.c:10197
#18 mjs_op_json_parse (mjs=0x666010) at mjs.c:10246
#19 0x0000000000417048 in mjs_execute (mjs=0x666010, off=309, res=0x7fffffffe4d8) at mjs.c:7902
#20 0x0000000000411a01 in mjs_exec_internal (mjs=0x666010, path=<optimized out>, src=<optimized out>,
    generate_jsc=<optimized out>, res=0x7fffffffe5b0) at mjs.c:8106
#21 0x000000000041d749 in mjs_exec_file (mjs=<optimized out>,
    path=0x7fffffffe8ed "out_20181119_22_31_58/crash/w01_000020,sig:11,Splice:69:573,src:w01_001293",
    res=<optimized out>) at mjs.c:8129
#22 main (argc=<optimized out>, argv=0x7fffffffe6e8) at mjs.c:10302
```


Input: `out_20181119_22_31_58/crash/w01_000030,sig:6,Havoc:26747:27520,src:w01_001635`
```
mjs_main: mjs.c:7782: mjs_err_t mjs_execute(struct mjs *, size_t, mjs_val_t *): Assertion `mjs_stack_size(&mjs->scopes) > 0' failed.

Program received signal SIGABRT, Aborted.
0x00007ffff783e428 in __GI_raise (sig=sig@entry=6) at ../sysdeps/unix/sysv/linux/raise.c:54
54      ../sysdeps/unix/sysv/linux/raise.c: No such file or directory.
```
```
#0  0x00007ffff783e428 in __GI_raise (sig=sig@entry=6) at ../sysdeps/unix/sysv/linux/raise.c:54
#1  0x00007ffff784002a in __GI_abort () at abort.c:89
#2  0x00007ffff7836bd7 in __assert_fail_base (fmt=<optimized out>,
    assertion=assertion@entry=0x440a37 "mjs_stack_size(&mjs->scopes) > 0", file=file@entry=0x440194 "mjs.c",
    line=line@entry=7782, function=function@entry=0x440a58 "mjs_err_t mjs_execute(struct mjs *, size_t, mjs_val_t *)")
    at assert.c:92
#3  0x00007ffff7836c82 in __GI___assert_fail (assertion=0x440a37 "mjs_stack_size(&mjs->scopes) > 0",
    file=0x440194 "mjs.c", line=7782, function=0x440a58 "mjs_err_t mjs_execute(struct mjs *, size_t, mjs_val_t *)")
    at assert.c:101
#4  0x000000000041bf06 in mjs_execute (mjs=0x666010, off=94, res=0x7fffffffe4d8) at mjs.c:7782
#5  0x0000000000411a01 in mjs_exec_internal (mjs=0x666010, path=<optimized out>, src=<optimized out>,
    generate_jsc=<optimized out>, res=0x7fffffffe5b0) at mjs.c:8106
#6  0x000000000041d749 in mjs_exec_file (mjs=<optimized out>,
    path=0x7fffffffe8ea "out_20181119_22_31_58/crash/w01_000030,sig:6,Havoc:26747:27520,src:w01_001635",
    res=<optimized out>) at mjs.c:8129
#7  main (argc=<optimized out>, argv=0x7fffffffe6e8) at mjs.c:10302
```

Input: `out_20181119_22_31_58/crash/w01_000186,sig:11,Splice:1:16,src:w01_001735`
```
true
true

Program received signal SIGSEGV, Segmentation fault.
mjs_execute (mjs=0x666010, off=485, res=0x7fffffffe4d8) at mjs.c:7972
7972    mjs.c: No such file or directory.
```
```
#0  mjs_execute (mjs=0x666010, off=485, res=0x7fffffffe4d8) at mjs.c:7972
#1  0x0000000000411a01 in mjs_exec_internal (mjs=0x666010, path=<optimized out>, src=<optimized out>,
    generate_jsc=<optimized out>, res=0x7fffffffe5b0) at mjs.c:8106
#2  0x000000000041d749 in mjs_exec_file (mjs=<optimized out>,
    path=0x7fffffffe8ef "out_20181119_22_31_58/crash/w01_000186,sig:11,Splice:1:16,src:w01_001735",
    res=<optimized out>) at mjs.c:8129
#3  main (argc=<optimized out>, argv=0x7fffffffe6e8) at mjs.c:10302
```