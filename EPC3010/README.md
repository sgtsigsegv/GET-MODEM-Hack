# EPC3010
  
The EPC3010 contains a Broadcom BCM3080 processor accompanied by a 4MB SPI EEPROM.


Entropy of the EEPROM flash:
![Entropy](EPC3010-entropy.png)

The EEPROM is partitioned into six partitions. Two LZMA compressed ones, and two four unknown parts:

```
|---------------------|
| Firmware loader     |
| ------------------- |
| Certificates        |
| ------------------  |
| Main BCM Firmware   |
| ------------------- |
| Unknown MIPS Data   |
| ------------------- |
| Unknown data        |
| ------------------- |
| Logs                |
| ------------------- |
```


The LZMA compressed partition starting at `0x2005C` contains the main BCM MIPS firmware.

The second LZMA compressed blob starting at `0x20005C` is an unkown MIPS firmware.