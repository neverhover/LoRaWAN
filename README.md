# LoRaWAN
This is a LoRaWAN v1.0 implementation in python.

See: https://www.lora-alliance.org/portals/0/specs/LoRaWAN%20Specification%201R0.pdf

## Installation
Just git clone to your python source directory where you want to use this module.

## Example
```
#!/usr/bin/env python2.7
import LoRaWAN

nwkskey = [0x2b, 0x7e, 0x15, 0x16, 0x28, 0xae, 0xd2, 0xa6, 0xab, 0xf7, 0x15, 0x88, 0x09, 0xcf, 0x4f, 0x3c]
packet = [0x80,0x8f,0x77,0xbb,0x07,0x00,0x02,0x00,0x06,0xbd,0x33,0x42,0xa1,0x9f,0xcc,0x3c,0x8d,0x6b,0xcb,0x5f,0xdb,0x05,0x48,0xdb,0x4d,0xc8,0x50,0x14,0xae,0xeb,0xfe,0x0b,0x54,0xb1,0xc9,0x98,0xde,0xf5,0x3e,0x97,0x9b,0x70,0x1d,0xab,0xb0,0x45,0x30,0x0e,0xf8,0x69,0x9c,0x38,0xfc,0x1a,0x34,0xd5]

lorawan = LoRaWAN.new(packet)
print lorawan.get_mtype()
print lorawan.get_mversion()
print map(hex, lorawan.get_mic())
print map(hex, bytearray(lorawan.compute_mic(nwkskey)))
print bytearray(lorawan.decrypt_payload(nwkskey))
```
