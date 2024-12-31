# Motorola SM8635 Kernel Build Manifest

To build:

1. Initialize sources:

```bash
repo init -u https://github.com/Kendrenogen-moto-sm8635/android_kernel_manifest.git -b stock --depth=1
```

2. Sync the sources:

```bash
repo sync -j$(nproc --all)
```

2a. Unshallow relevant repos to allow for committing changes to relevant repos:

```bash
cd kernel_platform/msm-kernel
git pull --unshallow
git checkout stock
cd ../script
git pull --unshallow
git checkout stock
cd ../common
git pull --unshallow
git checkout stock
cd ../qcom/proprietary/devicetree
git pull --unshallow
git checkout stock
cd ../../../../vendor/nxp/opensource/driver
git pull --unshallow
git checkout stock
cd ../../../qcom/opensource/audio-kernel
git pull --unshallow
git checkout stock
cd ../bt-kernel
git pull --unshallow
git checkout stock
cd ../camera-kernel
git pull --unshallow
git checkout stock
cd ../dataipa
git pull --unshallow
git checkout stock
cd ../datarmnet
git pull --unshallow
git checkout stock
cd ../datarmnet-ext
git pull --unshallow
git checkout stock
cd ../display-drivers
git pull --unshallow
git checkout stock
cd ../dsp-kernel
git pull --unshallow
git checkout stock
cd ../eva-kernel
git pull --unshallow
git checkout stock
cd ../fingerprint
git pull --unshallow
git checkout stock
cd ../graphics-kernel
git pull --unshallow
git checkout stock
cd ../mm-drivers
git pull --unshallow
git checkout stock
cd ../mmrm-driver
git pull --unshallow
git checkout stock
cd ../mm-sys-kernel
git pull --unshallow
git checkout stock
cd ../securemsm-kernel
git pull --unshallow
git checkout stock
cd ../spu-kernel
git pull --unshallow
git checkout stock
cd ../synx-kernel
git pull --unshallow
git checkout stock
cd ../touch-drivers
git pull --unshallow
git checkout stock
cd ../video-driver
git pull --unshallow
git checkout stock
cd ../wlan/fw-api
git pull --unshallow
git checkout stock
cd ../platform
git pull --unshallow
git checkout stock
cd ../qca-wifi-host-cmn
git pull --unshallow
git checkout stock
cd ../qcacld-3.0
git pull --unshallow
git checkout stock
cd ../../../proprietary/audio-devicetree
git pull --unshallow
git checkout stock
cd ../biometrics-fingerprint-devicetree
git pull --unshallow
git checkout stock
cd ../bt-devicetree
git pull --unshallow
git checkout stock
cd ../camera-devicetree
git pull --unshallow
git checkout stock
cd ../data-devicetree
git pull --unshallow
git checkout stock
cd ../display-devicetree
git pull --unshallow
git checkout stock
cd ../dsp-devicetree
git pull --unshallow
git checkout stock
cd ../eSE-devicetree
git pull --unshallow
git checkout stock
cd ../eva-devicetree
git pull --unshallow
git checkout stock
cd ../graphics-devicetree
git pull --unshallow
git checkout stock
cd ../mm-devicetree
git pull --unshallow
git checkout stock
cd ../mmrm-devicetree
git pull --unshallow
git checkout stock
cd ../mm-sys-devicetree
git pull --unshallow
git checkout stock
cd ../nfc-devicetree
git pull --unshallow
git checkout stock
cd ../synx-devicetree
git pull --unshallow
git checkout stock
cd ../video-devicetree
git pull --unshallow
git checkout stock
cd ../wlan-devicetree
git pull --unshallow
git checkout stock
cd ../../../st/opensource/driver
git pull --unshallow
git checkout stock
cd ../eSE-driver
git pull --unshallow
git checkout stock
cd ../../../../motorola/kernel/modules
git pull --unshallow
git checkout stock
cd ../../../
```
NOTE: 'stock' is the branch of the main kernel GitHub repo. You can replace this with whatever branch you like

3. Compile the kernel:

```bash
./build.sh pineapple SKU
```

where 'SKU' is either 'arcfox' for the Motorola Razr+ 2024/Razr 50 Ultra, or 'ctwo' for the Moyotola Edge 50 Ultra
