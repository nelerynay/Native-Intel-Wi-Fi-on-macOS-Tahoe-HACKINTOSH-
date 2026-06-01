# Guide for Native Intel Wi-Fi on Tahoe

What you need
- Supported Intel Wi-Fi card from [OpenIntelWireless' Page](https://openintelwireless.github.io/itlwm/Compat.html)
- MacOS Tahoe
- [Airportitlwm latest version for **Ventura**](https://github.com/OpenIntelWireless/itlwm/releases/tag/v2.3.0)
- [IOSkywalkFamily.kext and IO80211FamilyLegacy.kext](https://github.com/dortania/OpenCore-Legacy-Patcher/tree/main/payloads/Kexts/Wifi)
- [Hackintosh WiFi patch script](https://github.com/rexchou/Hackintosh_script/blob/main/pacth_wifi.sh)

# Before you started
Before you started, make sure you do these things
- AMFI bypass using the boot-arg `amfi_get_out_of_my_way=0x1`
- SIP disabled on NVRAM

# DISCLAIMER
The Wi-Fi patch script is using Chinese Language, in order to run the script properly **please make sure you have a translator**

other way, it might not work properly and can resulting kernel panic

# Let's cook
1. Add the **3 kext** that already downloaded and moved to the `EFI/OC/Kexts`
2. Open your config.plist, under `kext>block` add
   |Identifier                       |Comment                  |Enabled|Strategy|MinKernel|MaxKernel|Arch|
   |---------------------------------|-------------------------|-------|--------|---------|---------|----|
   |com.apple.ioskit.IOSKywalkFamily |Allow IOSkywalk Downgrade|True   |Exclude |23.0.0   |         |Any |
   
   if this step skipped, the machine will unable to boot and **throw a kernel panic**
4. Add the kexts to your config.plist
5. Run the hackintosh script to patch wifi and allowing to run Intel native Wi-Fi (**READ DISCLAIMER**)
6. When it is done, restart your machine.

## Thank you!

Works on Intel AX210 Wi-Fi 6E, running macOS Tahoe 26.2
