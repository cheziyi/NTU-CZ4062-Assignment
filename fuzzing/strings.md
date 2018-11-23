GNU strings 2.15
Copyright 2004 Free Software Foundation, Inc.
This program is free software; you may redistribute it under the terms of
the GNU General Public License.  This program has absolutely no warranty.

Source: http://ftp.gnu.org/gnu/binutils/binutils-2.15.tar.bz2


Input: `out_20181119_22_32_03/crash/w01_000000,sig:11,Havoc:34:18304,src:w00_000000`
A null pointer dereference in function bfd_section_from_shdr()(elf.c:1657)
```
Program received signal SIGSEGV, Segmentation fault.
0x0000000000431c39 in bfd_section_from_shdr (abfd=0x71c080, shindex=515) at ../../bfd/elf.c:1657
1657    ../../bfd/elf.c: No such file or directory.
```
```
#0  0x0000000000431c39 in bfd_section_from_shdr (abfd=0x71c080, shindex=515) at ../../bfd/elf.c:1657
#1  0x0000000000477dbb in bfd_elf32_object_p (abfd=0x71c080) at ../../bfd/elfcode.h:689
#2  0x0000000000408d91 in bfd_check_format_matches (abfd=0x71c080, format=<optimized out>, matching=0x0)
    at ../../bfd/format.c:228
#3  0x000000000040298f in strings_object_file (file=<optimized out>) at ../../binutils/strings.c:350
#4  strings_file (file=<optimized out>) at ../../binutils/strings.c:380
#5  main (argc=2, argv=0x7fffffffe6d8) at ../../binutils/strings.c:298
```
bfd/elf.c
```
1652  Elf_Internal_Shdr *hdr = elf_elfsections (abfd)[shindex];
1653  Elf_Internal_Ehdr *ehdr = elf_elfheader (abfd);
1654  const struct elf_backend_data *bed = get_elf_backend_data (abfd);
1655  const char *name;
1656
1657  name = elf_string_from_elf_strtab (abfd, hdr->sh_name);
```
```
(gdb) p abfd
$1 = (bfd *) 0x71c080
(gdb) p hdr
$3 = (Elf_Internal_Shdr *) 0x0
(gdb) p hdr->sh_name
Cannot access memory at address 0x0
```



Input: `out_20181119_22_32_03/crash/w01_000026,sig:11,Splice:1:16,src:w01_000093`
A null pointer dereference in function bfd_section_from_shdr()(elf.c:1652)
```
Program received signal SIGSEGV, Segmentation fault.
0x0000000000431c2a in bfd_section_from_shdr (abfd=0x71c080, shindex=924872556) at ../../bfd/elf.c:1652
1652    in ../../bfd/elf.c
```
```
#0  0x0000000000431c2a in bfd_section_from_shdr (abfd=0x71c080, shindex=924872556) at ../../bfd/elf.c:1652
#1  0x0000000000432875 in bfd_section_from_shdr (abfd=0x71c080, shindex=3) at ../../bfd/elf.c:1751
#2  0x0000000000477dbb in bfd_elf32_object_p (abfd=0x71c080) at ../../bfd/elfcode.h:689
#3  0x0000000000408d91 in bfd_check_format_matches (abfd=0x71c080, format=<optimized out>, matching=0x0)
    at ../../bfd/format.c:228
#4  0x000000000040298f in strings_object_file (file=<optimized out>) at ../../binutils/strings.c:350
#5  strings_file (file=<optimized out>) at ../../binutils/strings.c:380
#6  main (argc=2, argv=0x7fffffffe6e8) at ../../binutils/strings.c:298
```
bfd/elf.c
```
1652  Elf_Internal_Shdr *hdr = elf_elfsections (abfd)[shindex];
1653  Elf_Internal_Ehdr *ehdr = elf_elfheader (abfd);
1654  const struct elf_backend_data *bed = get_elf_backend_data (abfd);
1655  const char *name;
1656
1657  name = elf_string_from_elf_strtab (abfd, hdr->sh_name);
```
```
(gdb) p abfd
$4 = (bfd *) 0x71c080
(gdb) p shindex
$5 = 924872556
(gdb) p *abfd
$6 = {id = 0, filename = 0x7fffffffe8e8 "out_20181119_22_32_03/crash/w01_000026,sig:11,Splice:1:16,src:w01_000093",
  xvec = 0x4e4828 <bfd_elf32_little_generic_vec>, iostream = 0x71e1d0, cacheable = 1, target_defaulted = 1,
  lru_prev = 0x71c080, lru_next = 0x71c080, where = 3439329535, opened_once = 0, mtime_set = 0, mtime = 0, ifd = 0,
  format = bfd_object, direction = read_direction, flags = 256, origin = 0, output_has_begun = 0, section_htab = {
    table = 0x720430, size = 4051, newfunc = 0x40d330 <bfd_section_hash_newfunc>, memory = 0x71f410}, sections = 0x0,
  section_tail = 0x71c110, section_count = 0, start_address = 4278222956, symcount = 0, outsymbols = 0x0,
  dynsymcount = 0, arch_info = 0x4d5820 <bfd_default_arch_struct>, arelt_data = 0x0, my_archive = 0x0, next = 0x0,
  archive_head = 0x0, has_armap = 0, link_next = 0x0, archive_pass = 0, tdata = {aout_data = 0x71c1e0,
    aout_ar_data = 0x71c1e0, oasys_obj_data = 0x71c1e0, oasys_ar_data = 0x71c1e0, coff_obj_data = 0x71c1e0,
    pe_obj_data = 0x71c1e0, xcoff_obj_data = 0x71c1e0, ecoff_obj_data = 0x71c1e0, ieee_data = 0x71c1e0,
    ieee_ar_data = 0x71c1e0, srec_data = 0x71c1e0, ihex_data = 0x71c1e0, tekhex_data = 0x71c1e0,
    elf_obj_data = 0x71c1e0, nlm_obj_data = 0x71c1e0, bout_data = 0x71c1e0, mmo_data = 0x71c1e0,
    sun_core_data = 0x71c1e0, sco5_core_data = 0x71c1e0, trad_core_data = 0x71c1e0, som_data = 0x71c1e0,
    hpux_core_data = 0x71c1e0, hppabsd_core_data = 0x71c1e0, sgi_core_data = 0x71c1e0, lynx_core_data = 0x71c1e0,
    osf_core_data = 0x71c1e0, cisco_core_data = 0x71c1e0, versados_data = 0x71c1e0, netbsd_core_data = 0x71c1e0,
    mach_o_data = 0x71c1e0, mach_o_fat_data = 0x71c1e0, pef_data = 0x71c1e0, pef_xlib_data = 0x71c1e0,
    sym_data = 0x71c1e0, any = 0x71c1e0}, usrdata = 0x0, memory = 0x71c1b0}
```



Input: `out_20181119_22_32_03/crash/w01_000030,sig:11,Splice:6:16,src:w01_000198`
A null pointer dereference in function bfd_hash_lookup()(hash.c:374)
```
Program received signal SIGSEGV, Segmentation fault.
0x000000000040f8ee in bfd_hash_lookup (table=0x71c0f0, string=0x0, create=1, copy=0) at ../../bfd/hash.c:374
374     ../../bfd/hash.c: No such file or directory.
```
```
#0  0x000000000040f8ee in bfd_hash_lookup (table=0x71c0f0, string=0x0, create=1, copy=0) at ../../bfd/hash.c:374
#1  0x000000000040daa4 in bfd_make_section_anyway (abfd=0x71c080, name=0x0) at ../../bfd/section.c:941
#2  0x000000000042c25c in _bfd_elf_make_section_from_shdr (abfd=0x71c080, hdr=0x71c790, name=0x0)
    at ../../bfd/elf.c:651
#3  0x0000000000431ca7 in bfd_section_from_shdr (abfd=0x71c080, shindex=<optimized out>) at ../../bfd/elf.c:1672
#4  0x0000000000477dbb in bfd_elf32_object_p (abfd=0x71c080) at ../../bfd/elfcode.h:689
#5  0x0000000000408d91 in bfd_check_format_matches (abfd=0x71c080, format=<optimized out>, matching=0x0)
    at ../../bfd/format.c:228
#6  0x000000000040298f in strings_object_file (file=<optimized out>) at ../../binutils/strings.c:350
#7  strings_file (file=<optimized out>) at ../../binutils/strings.c:380
#8  main (argc=2, argv=0x7fffffffe6e8) at ../../binutils/strings.c:298
```
bfd/hash.c
```
371  hash = 0;
372  len = 0;
373  s = (const unsigned char *) string;
374  while ((c = *s++) != '\0')
```
```
(gdb) p s
$8 = (const unsigned char *) 0x1 <error: Cannot access memory at address 0x1>
```



Input: `out_20181119_22_32_03/crash/w01_000080,sig:11,Havoc:47:1144,src:w01_000725`
A null pointer dereference in function bfd_alloc()(opncls.c:652)
```
Program received signal SIGSEGV, Segmentation fault.
bfd_alloc (abfd=0x363f363636363636, size=7) at ../../bfd/opncls.c:652
652     ../../bfd/opncls.c: No such file or directory.
```
```
#0  bfd_alloc (abfd=0x363f363636363636, size=7) at ../../bfd/opncls.c:652
#1  0x0000000000416405 in first_phase (abfd=<optimized out>, type=<optimized out>, src=<optimized out>)
    at ../../bfd/tekhex.c:458
#2  pass_over (abfd=<optimized out>, func=<optimized out>) at ../../bfd/tekhex.c:519
#3  tekhex_object_p (abfd=<optimized out>) at ../../bfd/tekhex.c:588
#4  0x0000000000408d91 in bfd_check_format_matches (abfd=0x71c080, format=<optimized out>, matching=0x0)
    at ../../bfd/format.c:228
#5  0x000000000040298f in strings_object_file (file=<optimized out>) at ../../binutils/strings.c:350
#6  strings_file (file=<optimized out>) at ../../binutils/strings.c:380
#7  main (argc=2, argv=0x7fffffffe6e8) at ../../binutils/strings.c:298
```
bfd/opncls.c
```
644  void *ret;
645
646  if (size != (unsigned long) size)
647    {
648      bfd_set_error (bfd_error_no_memory);
649      return NULL;
650    }
651
652  ret = objalloc_alloc (abfd->memory, (unsigned long) size);
```
```
(gdb) p abfd
$9 = (bfd *) 0x363f363636363636
(gdb) p abfd->memory
Cannot access memory at address 0x363f36363636374e
(gdb) p *abfd
Cannot access memory at address 0x363f363636363636
(gdb) p size
$10 = 7
```



Input: `out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202`
A null pointer dereference in _bfd_elf_make_section_from_shdr bfd_alloc()(elf.c:746)
```
Program received signal SIGSEGV, Segmentation fault.
_bfd_elf_make_section_from_shdr (abfd=<optimized out>, hdr=0x71c6e0, name=<optimized out>) at ../../bfd/elf.c:746
746     in ../../bfd/elf.c
```
```
#0  _bfd_elf_make_section_from_shdr (abfd=<optimized out>, hdr=0x71c6e0, name=<optimized out>) at ../../bfd/elf.c:746
#1  0x0000000000432bcb in bfd_section_from_shdr (abfd=0x71c080, shindex=<optimized out>) at ../../bfd/elf.c:1936
#2  0x0000000000477dbb in bfd_elf32_object_p (abfd=0x71c080) at ../../bfd/elfcode.h:689
#3  0x0000000000408d91 in bfd_check_format_matches (abfd=0x71c080, format=<optimized out>, matching=0x0)
    at ../../bfd/format.c:228
#4  0x000000000040298f in strings_object_file (file=<optimized out>) at ../../binutils/strings.c:350
#5  strings_file (file=<optimized out>) at ../../binutils/strings.c:380
#6  main (argc=2, argv=0x7fffffffe6d8) at ../../binutils/strings.c:298
```
bfd/elf.c
```
744      for (i = 0; i < elf_elfheader (abfd)->e_phnum; i++, phdr++)
745	{
746	  if (phdr->p_paddr != 0)
747	    break;
748	}
```
```
(gdb) p phdr
$11 = (Elf_Internal_Phdr *) 0x0
(gdb) p phdr->p_paddr
Cannot access memory at address 0x20
```
































```
Starting program: /home/docker/test-strings-fot/strings out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid string offset 6553802 >= 120 for section `'
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid string offset 6553802 >= 120 for section `'
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid string offset 1179403647 >= 0 for section `'
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid SHT_GROUP entry
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid string offset 6553802 >= 120 for section `'
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid string offset 6553802 >= 120 for section `'
BFD: out_20181119_22_32_03/crash/w01_000130,sig:11,Havoc:603:1104,src:w01_001202: invalid string offset 1179403647 >= 0 for section `'
```