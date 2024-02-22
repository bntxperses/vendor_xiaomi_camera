# proprietary_vendor_xiaomi_camera

Prebuilt stock MIUI/Leica Camera for Poco F3/Redmi K40/Mi 11x (alioth), to include in custom ROM builds.

### How to use?

1. Clone this repo to `vendor/xiaomi/camera`

2. Inherit it from `device.mk` in device tree:

```
# Camera
$(call inherit-product-if-exists, vendor/xiaomi/camera/miuicamera.mk)
```

3. Ensure that you added misys vintf dependencies in your framework_compatibility_matrix.xml:

```
    <hal format="hidl" optional="true">
        <name>vendor.xiaomi.hardware.misys</name>
        <version>1.0</version>
        <interface>
            <name>IMiSys</name>
            <instance>default</instance>
        </interface>
    </hal>
    <hal format="hidl" optional="true">
        <name>vendor.xiaomi.hardware.misys</name>
        <version>2.0</version>
        <interface>
            <name>IMiSys</name>
            <instance>default</instance>
        </interface>
    </hal>
    <hal format="hidl" optional="true">
        <name>vendor.xiaomi.hardware.misys</name>
        <version>3.0</version>
        <interface>
            <name>IMiSys</name>
            <instance>default</instance>
        </interface>
    </hal>
    <hal format="hidl" optional="true">
        <name>vendor.xiaomi.hardware.misys</name>
        <version>4.0</version>
        <interface>
            <name>IMiSys</name>
            <instance>default</instance>
        </interface>
    </hal>
```
3.1 Reference - https://github.com/VoidUI-Devices/device_xiaomi_sm8250-common/commit/47e3f385a6cd16b0200a4bfd34cad1fba75ac210
