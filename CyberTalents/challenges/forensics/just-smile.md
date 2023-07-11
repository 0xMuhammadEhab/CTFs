- you will find `This_Is_Not_the_Flag_but_Useful` in comment section
```exiftool smile.png```
- when you check the type you will find that is normal png
- strings the image you will 
```
Say the password:
;*3$"
GCC: (Ubuntu 7.3.0-27ubuntu1~18.04) 7.3.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.7696
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
flag.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
_edata
__stack_chk_fail@@GLIBC_2.4
printf@@GLIBC_2.2.5
__libc_start_main@@GLIBC_2.2.5
__data_start
strcmp@@GLIBC_2.2.5
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
__isoc99_scanf@@GLIBC_2.7
__TMC_END__
```
- which mean that there is some of executable inside the image 
- delete from the begin of image untill reach the elf file header `^?ELF^`
``` file smile.png
smile.sh: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b69c1cf0ad3c9bc837a7e23139f321fc81238045, not stripped
```
- then 
```
ltrace ./smile.png
printf("Say the password:")                                                                                                                        = 17
__isoc99_scanf(0x55c80a400a26, 0x7ffd5cedc710, 0x6c75666573555f, 0Say the password:This_Is_Not_the_Flag_but_Useful
)                                                                                = 1
strcmp("This_Is_Not_the_Flag_but_Useful", "This_Is_Not_the_Flag_but_Useful")                                                                       = 0
printf("%s", "FLAG{XD}")                                                                                                    = 31
--- SIGSEGV (Segmentation fault) ---
+++ killed by SIGSEGV +++

```
