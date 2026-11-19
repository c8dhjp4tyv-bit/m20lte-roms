# Custom ROMs for the Samsung Galaxy M20 (m20lte)

## Official

| ROM | Android | Status | Download |
|---|---|---|---|
| **LineageOS 22.2** (official, weekly) | 15 | ✅ Tested | [download.lineageos.org/devices/m20lte](https://download.lineageos.org/devices/m20lte) |

Install guide: [wiki.lineageos.org/devices/m20lte/install](https://wiki.lineageos.org/devices/m20lte/install)

## Unofficial

Test builds on the Linux 5.10 kernel port. Signed with test keys.
Each ROM zip must be flashed with **its own recovery** from the same row.

| ROM | Android | Variant | Status | ROM zip | Recovery (Odin, AP) |
|---|---|---|---|---|---|
| RisingOS Revived 9 | 17 | GApps | ✅ Tested | [RisingOS-9-261119-1728-CORE-COMMUNITY-m20lte.zip](https://drive.google.com/file/d/16UaaD2BfmLai_Q4zOGdauo2ituE9dRVY/view?usp=sharing) | [RisingOS-9-m20lte-CORE-recovery.tar.md5](https://drive.google.com/file/d/1ksnDFDtnSdXBE9sGJ5sa2TnwiRwa47Ly/view?usp=sharing) |
| RisingOS Revived 9 | 17 | Vanilla | ⏳ Untested | [RisingOS-9-261119-1807-VANILLA-COMMUNITY-m20lte.zip](https://drive.google.com/file/d/1qg8F-aey--n-nHfNFiw4DJGQGZI0QJmc/view?usp=sharing) | [RisingOS-9-m20lte-VANILLA-recovery.tar.md5](https://drive.google.com/file/d/1ZKZ39vggXpRtRU7A-UY90FA6Rr4C9Nxf/view?usp=sharing) |
| Project Infinity X 4.2 | 17 | GApps | ⏳ Untested | [Project_Infinity-X-4.2-m20lte-19.11.2026-GAPPS-UNOFFICIAL.zip](https://drive.google.com/file/d/1NpiurifNjmIVrhIKPcByqw7vdFUW8gFW/view?usp=sharing) | [Infinity-X-4.2-m20lte-GAPPS-recovery.tar.md5](https://drive.google.com/file/d/1AUsZxXJTBuv-UUcGaoAYLVMpUEa4vVbj/view?usp=sharing) |
| Project Infinity X 4.2 | 17 | Vanilla | ⏳ Untested | [Project_Infinity-X-4.2-m20lte-19.11.2026-VANILLA-UNOFFICIAL.zip](https://drive.google.com/file/d/1JKtJJnU1IAnKtEdJ7wzGAXXxnTFdXlhZ/view?usp=sharing) | [Infinity-X-4.2-m20lte-VANILLA-recovery.tar.md5](https://drive.google.com/file/d/1J5dPBzVgeAiBxsY8UW9pzijXasTsyWXO/view?usp=sharing) |
| AxionOS 2.9 | 16 | GApps | ⏳ Untested | [axion-2.9-NOESIS-20261119-UNOFFICIAL-GMS-m20lte.zip](https://drive.google.com/file/d/1J5cCvflkEHROVn9vfRLntbsbu2HVALKi/view?usp=sharing) | [Axion-2.9-A16-m20lte-GMS-recovery.tar.md5](https://drive.google.com/file/d/1Kos8KLUkjTKS0raJtnVBTit7JxDGmQS4/view?usp=sharing) |

## Install (clean flash)

1. Odin (or `odin4` on Linux): put the recovery `.tar.md5` in **AP** and flash.
   Do not use heimdall with the `.tar.md5`, it writes the tar raw and the
   bootloader then shows "invalid kernel length".
2. Boot that recovery (Vol Up + Power).
3. Factory reset → **Format data** (needed when coming from another ROM).
4. Apply update → Apply from ADB → `adb sideload <rom>.zip`.
5. Reboot.

OrangeFox (4.4 kernel) cannot install these, the Android 16/17 installer
aborts with signal 6.

## Notes

- The system partition is EROFS (the ROMs do not fit the 3.4 GB ext4 system otherwise).
- Android 16 builds (Axion, Lunaris) have no VoLTE yet.
- Test builds: report problems with a log in the Telegram group.

## SHA-256

```
aaa99bab2885d1296e1d331bc4147586c4e0772e18b00b4af29a14da6df2b5c5  Axion-2.9-A16-m20lte-GMS-recovery.tar.md5
6137a97df9aceff3f89f1808ad62251b9f9f346bb56f78850930baf634e2f237  Infinity-X-4.2-m20lte-GAPPS-recovery.tar.md5
cbb964774a44c59532c8bbac3937a8f974b8e6a62d9f053a45778967d4b7c41f  Infinity-X-4.2-m20lte-VANILLA-recovery.tar.md5
52f41d9096a64b59c6a35484a2b81db044e426d091e8914ce164c23a6dfabf21  Project_Infinity-X-4.2-m20lte-19.11.2026-GAPPS-UNOFFICIAL.zip
7fe49af8b00b1088465d17f2ba862ef20a8a62c694107d6936a0d83896a18552  Project_Infinity-X-4.2-m20lte-19.11.2026-VANILLA-UNOFFICIAL.zip
bcfcbda65d69c455b926e0e6e3e987d737a5b93a3514a77b48b4f8fe339ceb52  RisingOS-9-261119-1728-CORE-COMMUNITY-m20lte.zip
59ba5bc6eb215b78fb1862d524e08905f205075746a5a2caf79601571b22b0da  RisingOS-9-261119-1807-VANILLA-COMMUNITY-m20lte.zip
a8b4611665e5c977f1e23fa8460b0528d4898f0f1666b0987737db5c775648ad  RisingOS-9-m20lte-CORE-recovery.tar.md5
4627265975b4f9f68d2d7a0bdb985026a7d9fc01b190d58f2c4881366630e420  RisingOS-9-m20lte-VANILLA-recovery.tar.md5
ee94bb5248133327a1f1c9ccff62517e3a2aade7847e99b0a177e0c265457c07  axion-2.9-NOESIS-20261119-UNOFFICIAL-GMS-m20lte.zip
```
