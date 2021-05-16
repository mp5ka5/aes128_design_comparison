# A Compact AES-128 Design
The table shows different design architectures of AES-128 and introduces a very compact and highly area optimization design which can provide a very high computation throughput over a traditional pipelined architecture.
<br/>
<br/>

Algorithm
------
[Advanced Encryption Standard (AES) Algorithm](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197.pdf)
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

![](Fig1.png)
<p align="center">
    Fig1. The Fmax of different optimization modes
</p>


![](Fig2.png)
<p align="center">
    Fig2. Overall comparison of different AES designs
</p>

![](Fig3.png)
<p align="center">
    Fig3. The max throughput comparison after aligning resource utilization
</p>