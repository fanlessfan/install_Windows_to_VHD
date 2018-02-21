# install_Windows_to_VHD
Instructions on how to install windows to vhd file

Step 1, Boot your computer using your Bootable Media (DVD or USB media)
Step 2, At the Install screen, press SHIFT+F10 to access the Command Window.
Step 3, Run diskpart command and type the following command: 
     list disk.
     select disk 0 (where 0 is the disk number)
     clean.
          (CAUTION:This will remove all partitions on the selected disk causing data lost.)
     convert gpt.
     create partition efi size=512
     create partition primary size=40960
     format fs=NTFS quick.
     assign letter=W
     Then type exit from diskpart
Step 4, Type mkdir w:\vdisk
Step 5, Run diskpart command again with below commands
     create vdisk file=”w:\vdisk\windows10.vhdx” maximum=25600 type=fixed
     attach vdisk
     exit
Step 6, exit the command window and click install now with "Custom: Install Windows only" and selct the vdisk just attached.
Step 7, Windows is now installing the operating system.
