# A Compact AES-128 Design
This design demonstrates Bitcoin mining using Intel Arria 10 SoC FPGA. The ARM processor reads block information given by user and completes a pre-computing of hash. The FPGA receives init data and finishes rest of computation with all possible nonces to produce hash blocks. For simplicity any produced block has 32-bit leading zeros is considered to be valid therefore the corresponding nonce will be collected and sent back to processor. The FPGA contains 7 fully pipelined computing engines and is able to complete job in less than 4 seconds.
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

xxxx

![](Fig2.png)
yyyy

![](Fig3.png)
zzzz
