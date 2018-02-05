# install_Windows_to_VHD
Instructions on how to install windows to vhd file

Step 1, Boot your computer using your Bootable Media (DVD or USB media)
Step 2, At the Install screen, press SHIFT+F10 to access the Command Window.
Type command: diskpart.
Type command: list disk.
Select the disk you want to use, type select disk 0 where 0 is the disk number.
Type clean.
CAUTION
This will remove all partitions on the selected disk causing data lost.
type convert gpt.
create partition efi size=512
create partition primary size=30720
Type format fs=NTFS quick.
Type assign letter=W
