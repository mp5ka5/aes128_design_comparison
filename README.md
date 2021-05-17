# A Compact AES-128 Design
Comparing different design architectures of AES-128 to show pros and cons of each strategy. Correclty merging these advantages can build a very compact design offering extremely high throughput over a traditional pipelined architecture.
<br/>
<br/>

Algorithm
------
[Advanced Encryption Standard (AES) Algorithm](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197.pdf)
<br/>
<br/>

Development Tool
------
Intel Quartus Prime Standard 18.1
<br/>
<br/>

Platform
------
[ARROW SoCKit](https://www.arrow.com/en/products/sockit/arrow-development-tools)
* Cyclone V SoC 5CSXFC6D6F31C8NES ver.B
* Dual-core ARM Cortex-A9 (HPS)
* 110K Programmable Logic Elements
* 5,140 Kbits embedded memory
<br/>

Comparison
------
Here is a quick shot to show all design sizes and Fmax values after applying different optimization efforts. 
Normally the decryption architecture is more complicated than the encryption one so the size is larger and the Fmax is lower. Notice the "Best Performance" compilation effort does not always guarantee the best Fmax result.
<br/>
![](Fig1.png)
<p align="center">
    Fig1. The Fmax of different optimization modes
</p>
<br/>

The *aes_inv_cipher_top* and *aes_cipher_top* are open source from website. 

The *Aes128Word* runs enryption flow and most operations inside uses 32-bit data, not the full 128-bit data. The strategy to reduce size does not come out a good result and the Fmax has no improvement.

The *Aes128DecPipe* is a pipelined architecture for decryption which targets to create the max throughput.

The *Aes128EnDeV2* merges encryption and decryption in one design therefore resources can be shared. Some architecture improvement extends the computing cycle. Low Fmax and long cycle comes out the worst performance.

The *ProcElemAes128V3* combines pros of previos designs and targets to be the most compact AES module. Though the computing cycle is long, the size is extremely small and is capable to be executed at very high clock rate. 
<br/>
![](Fig2.png)
<p align="center">
    Fig2. Overall comparison of different AES designs
</p>
<br/>

To compare the performance, assuming 26% utilization for all designs concludes the *ProcElemAes128V3* can provide computing power over 4G blocks per sec which is an extremely high performance on a 28nm FPGA.
<br/>
![](Fig3.png)
<p align="center">
    Fig3. The max throughput comparison after aligning resource utilization
</p>

