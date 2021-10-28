NVENC and NvFBC patches for Nvidia drivers
==========================================


[NVENC patch](patch.sh) removes restriction on maximum number of simultaneous NVENC video encoding sessions imposed by Nvidia to consumer-grade GPUs.




## Version Table

| 465.19.01 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/465.19.01/NVIDIA-Linux-x86_64-465.19.01.run) |
| 465.24.02 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/465.24.02/NVIDIA-Linux-x86_64-465.24.02.run) |
| 465.27 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/465.27/NVIDIA-Linux-x86_64-465.27.run) |
| 465.31 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/465.31/NVIDIA-Linux-x86_64-465.31.run) |
| 470.42.01 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/470.42.01/NVIDIA-Linux-x86_64-470.42.01.run) |
| 470.57.02 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/470.57.02/NVIDIA-Linux-x86_64-470.57.02.run) |
| 470.62.02 | YES | YES |  |
| 470.62.05 | YES | YES |  |
| 470.63.01 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/470.63.01/NVIDIA-Linux-x86_64-470.63.01.run) |
| 470.74 | YES | YES | [Driver link](https://international.download.nvidia.com/XFree86/Linux-x86_64/470.74/NVIDIA-Linux-x86_64-470.74.run) |

# bash ./patch.sh -h

SYNOPSIS
       patch.sh [-s] [-r|-h|-c VERSION|-l|-f]

DESCRIPTION
       The patch for Nvidia drivers to remove NVENC session limit

       -s             Silent mode (No output)
       -r             Rollback to original (Restore lib from backup)
       -h             Print this help message
       -c VERSION     Check if version VERSION supported by this patch.
                      Returns true exit code (0) if version is supported.
       -l             List supported driver versions
       -d VERSION     Use VERSION driver version when looking for libraries
                      instead of using nvidia-smi to detect it.
       -f             Enable support for Flatpak NVIDIA drivers.

```

## Install

```
./patch.sh -r
Detected nvidia driver version: 470.63.01
Restore from backup libnvidia-encode.so.470.63.01
root@41684:~/nvidia-patch# ./patch.sh 
Detected nvidia driver version: 470.63.01
18b4249e6513b77a69b26c3212c5779736d749a3  /opt/nvidia/libnvidia-encode-backup/libnvidia-encode.so.470.63.01
29da0846e54cc1de195ed2efa4aa01388d469a48  /usr/lib/x86_64-linux-gnu/libnvidia-encode.so.470.63.01
Patched!


```
## Rollback

If something got broken you may restore patched driver from backup:

```bash
bash ./patch.sh -r
```

