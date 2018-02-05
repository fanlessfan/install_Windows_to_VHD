# install_Windows_to_VHD
Instructions on how to install windows to vhd file

Step 1, Boot your computer using your Bootable Media (DVD or USB media)
Step 2, At the Install screen, press SHIFT+F10 to access the Command Window.
Type the following command: 
diskpart.
list disk.
select disk 0 (where 0 is the disk number)
clean.
     (CAUTION:This will remove all partitions on the selected disk causing data lost.)
convert gpt.
create partition efi size=512
create partition primary size=30720
format fs=NTFS quick.
assign letter=W
