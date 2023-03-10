# NuOsTheorySpring23
Kernal Assignment


**step 1** 
after downloading a kernel  extract it  and then go inside the linux folder
create a new folder and name it hello (since we are making a hello world system call)
then go inside that folder


**step 2**
open the terminal in folder and make a c code file by typing gedit hello.c
and type the following code

#include <linux/kernel.h>
asmlinkage long sys_hello(void)
{
printk("Hello world\n");
return 0;
}


**step 3**
now create a makefile  by typing makefile and put obj-y:=hello.o
 ![image](https://user-images.githubusercontent.com/87450783/224329495-283d98b9-9645-44fc-bfb4-eb9cf38c0a87.png)



**step 4**
go into the directory in /arch/x86/entry/syscalls/syscall_64.tbl.
and edit a system call 
![image](https://user-images.githubusercontent.com/87450783/224329898-2f2ffb01-b759-4a7e-ae93-5870d8c8c763.png)


**step 5**
type gedit include/linux/syscalls.h and paste the prototype of function hello in end of file
![image](https://user-images.githubusercontent.com/87450783/224330074-e5d01b56-5a20-4044-b316-35480ae9487e.png)


**step 6**
changing version and editing hello system call type make file and edit extraversion=-213064
and edit hello/ after core-y

![image](https://user-images.githubusercontent.com/87450783/224330267-e35bacfb-9df7-482b-b45b-013d4b2a9a60.png)
![image](https://user-images.githubusercontent.com/87450783/224330372-20cdf9a4-85a5-4c84-9233-a539379e316c.png)




**step 7**
type ls /boot |grep config
copy the config of current kernel into new one

![image](https://user-images.githubusercontent.com/87450783/224330475-d809d8bb-2a65-4274-bfdf-9a5c6cf53992.png)



**step 8**
clean kernel by typing make clean -j2 and then type make -j2

![image](https://user-images.githubusercontent.com/87450783/224330605-a1e78545-7d43-41d8-a961-0acd57305e63.png)

![image](https://user-images.githubusercontent.com/87450783/224330678-8f69ed02-6831-4276-b8d5-457818c2fe09.png)




**step 9**
now we have to install kernel 
type sudo make modules_install install

![image](https://user-images.githubusercontent.com/87450783/224330774-983adc4c-26a7-4059-a663-172d6a8b85d7.png)

 now restart by shutdown -r


**step 10**
enter uname -r in terminal 
![image](https://user-images.githubusercontent.com/87450783/224330875-1febc109-c9e9-4ed1-b690-b23c791578d5.png)


**step 11**
make a userspace file and type the following code in screenshot
![image](https://user-images.githubusercontent.com/87450783/224330955-dce6bef0-4e0e-414d-a176-839f4e9b65fd.png)
![image](https://user-images.githubusercontent.com/87450783/224331064-d1669cf3-2c83-4e7e-94d3-c22320ddd7e3.png)

and here it is our hello world in the last screenshot after running dmesg command
![image](https://user-images.githubusercontent.com/87450783/224331155-b0a09ed4-3cd0-469b-a4d9-07d3458da747.png)



