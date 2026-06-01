# Questions and Troubleshooting

###  1. Will it work on broadcom?
uhh... I don't know? Try to patch it using [OCLP](https://github.com/dortania/OpenCore-Legacy-Patcher)

### 2. My firefox doesn't work with `amfi_get_out_of_my_way=1` boot-arg
add ipc_control_port_options=0 to your boot-arg

### 3. I don't have bluetooth on
add `bluetoothExternalDongleFailed` and `bluetoothInternalControllerInfo` to your NVRAM
|key                            |Type|Value                          |
|-------------------------------|----|-------------------------------|
|bluetoothExternalDongleFailed  |Data|00                             |
|bluetoothInternalControllerInfo|Data|00000000 00000000 00000000 0000|

### 4. is this a permanent fix for native wifi on Tahoe?
I don't know, probably it is since Apple dropped Intel-based Macs on Tahoe, but let's see the future..
