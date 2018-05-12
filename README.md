# DRAM-note

This is a note for some background knowledge of DRAM for personal use, summarized from [蜗窝科技's blogs](http://www.wowotech.net/basic_tech/307.html). Please refer to the link for more detail information, and do not use this note for commercial purpose.

## DRAM storage cell

### Simple model

Fig. 1 shows a simple example of 1T1C (1 transistor 1 capacitor) DRAM cell, the reference voltage is V<sub>cc</sub>/2
<div align=center>
<img src="./dram_storage_cell.png"><br>Fig. 1 DRAM cell example
</div>
The 0/1 information is stored on the capacitor. When the voltage of wordline is high, the information can be accessed/modified by the bitline.

### Problem of the simple model

1. Capacitor of the bitline is much larger than the storage capacitor
2. Voltage of the storage capacitor is changed after accessed
3. Leakage of charge leads to storage capacitor voltage's decay

To solve all these problems, the Differential Sense Amplifier is introduced.

### Differential Sense Amplifier

Sensing Circuit and Voltage Equalization Circuit are added to Fig. 1, shown in Fig. 2.

<div align=center>
<img src="./differential_sense_amplifier.png")<br>Fig. 2 Differential Sense Amplifier
</div>

The read operation is performed in four steps, namely **Precharge**, **Access**, **Sense**, **Restore**. The write operation is performed in five steps, namely **Precharge**, **Access**, **Sense**, **Restore**, **Write Recovery**.

- Precharge

  Set EQ = 1, T<sub>e1</sub>, T<sub>e2</sub>, and T<sub>e3</sub> are conducted, the voltage of Bitline and /Bitline is set to V<sub>ref</sub>=V<sub>cc</sub>/2
  <div align=center>
  <img src="./precharge.png")<br>Fig. 3 Precharge
  </div>

