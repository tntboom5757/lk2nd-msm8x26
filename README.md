# lk2nd-msm8x26
These are the lk2nd binaries for the Lumias that have the chipset msm8x26

WINDOWS IS NEEDED

# Usage: Your bootloader must be unlocked. Go to @imbusho's repo and grab a copy of boot shim. (The elf version for this emmc_appsboot.mbn) 
Then, put the Lumia in Mass Storage Mode via WPInternals.
Next, open a CMD window as admin.
Then, browse to this directory of your Lumia. cd /d <lumia driveletter>/EFIESP/efi/Microsoft/Boot
Next, edit the BCD of your lumia in that terminal that should still be open.
(First, type bcdedit.exe /store .\BCD /enum ALL)
(Second, find the mention of "resetphone.efi". Copy the GUID above.)
(Finally, type bcdedit.exe /store .\BCD /set <GUID> NoIntegrityChecks yes)
Go to WolfLink115's repo for edk2. https://github.com/WolfLink115/edk2-msm8x26-lumia/tree/master/Lumia830Pkg
And download the Stage2.efi from the releases page.
And lastly, you want to copy the emmc_appsboot.mbn from this repo into the root of the EFIESP partition/directory, rename BootShim.efi, to resetphone.efi and place the new resetphone.efi file in MAINOS/EFIESP/Windows/System32/Boot.
