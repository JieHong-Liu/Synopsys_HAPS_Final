# Design and Verification of a 5-Stage Pipelined Processor with R-Format Instruction using Synopsys HAPS-100 Protocompiler

## Introduction:
In this project, we aim to design and verify a 5-stage pipelined processor with R-format instruction using the Synopsys HAPS-100 protocompiler. The pipeline processor is a fundamental building block of many modern microprocessors, and the R-format instruction is a type of instruction commonly used in MIPS (Microprocessor without Interlocked Pipeline Stage) architectures.


## Objective:
The objective of this project is to design and verify a 5-stage pipelined processor with R-format instruction using Synopsys HAPS-100 protocompiler. The HAPS-100 protocompiler will be used to validate the RTL design of the processor and run the partition flow to end up with a system-generated output.


## Block Diagram

+ The block diagram is as below:
    + ![](https://i.imgur.com/yWWlmaw.png)

+ This CPU read the 32-bit instruction and support below R-format instructions
    + ![](https://i.imgur.com/mj3dEyU.png)

## The Schemetic of FPGA_A and FPGA_B:

![](https://i.imgur.com/8OFaqeU.png)

+ FPGA_A
    + ![](https://i.imgur.com/OaEseei.png)
+ FPGA_B
    + ![](https://i.imgur.com/0ZPZRll.png)
    + ![](https://i.imgur.com/9uA2F13.png)
        + Adder
        + ![](https://i.imgur.com/jRBF2Op.png)


## Methodology:
The project will be divided into two main phases: design and verification. In the design phase, we will use Verilog to design the 5-stage pipelined processor with R-format instruction. The design will include modules for instruction fetch, instruction decode, instruction execute, memory access, and write-back.

In the verification phase, we will use Synopsys HAPS-100 protocompiler to validate the RTL design of the processor. We will use the HAPS-100 protocompiler to run the partition flow, which will partition the design into multiple parts and generate a system-generated output. We will then perform functional verification to ensure that the design meets the required specifications.

## Expected Outcome:
The expected outcome of this project is a 5-stage pipelined processor with R-format instruction that is fully verified using Synopsys HAPS-100 protocompiler. The design will meet the required specifications, and the verification results will be presented in a report.

## Timing Report and other Experimental Results

+ System Generate Result
    + ![](https://i.imgur.com/wKAJvV6.png)
+ The `.bit` file is generate by this flow.
    + Since we partition the design into two part, there are 2 `.bit` would be generate in the directory.
    + ![](https://i.imgur.com/GV7Rm0L.png)
    + ![](https://i.imgur.com/adOuqju.png)

+ Design Timing Summary
    + Since we partition the design into two part, there are 2 timing report would be generate in the directory.
        + Setup time: Check WNS and TNS in `FB1_uA_timing_summary.txt` and FB1_uB_timing_summary.txt`
            + ![](https://i.imgur.com/czDzdkG.png)
            + ![](https://i.imgur.com/FWv3GKr.png)
        + Hold time: Check WNS and THS in `FB1_uA_timing_summary_Min.txt` and `FB1_uB_timing_summary_Min.txt`
            + ![](https://i.imgur.com/CwCAfVL.png)
            + ![](https://i.imgur.com/cNckWIX.png)
    + Finally, all user specified timing constraints are met (no negative value).

## Conclusion & Reflection:

This project aims to design and verify a 5-stage pipelined processor with R-format instructions using the Synopsys HAPS-100 protocompiler. The project will provide hands-on experience in designing and verifying complex digital systems using industry-standard tools. The outcome of the project will be a verified design of a fundamental building block of modern microprocessors, which can serve as a starting point for further research and development.

During this project, I spent a lot of time resolving a schematic bug. My design is optimized by HAPS, so that my total schemetic diagram is optimized by below figure.
![](https://i.imgur.com/Rjxohwf.png)

After referencing the HAPS document, I added the comment /* synthesis syn_black_box */ in my RTL code, as shown in the figure below, and this flow worked smoothly.
![](https://i.imgur.com/fPYQYe2.png)

In the end, all timing constraints were met, which proves the functionality of my design and its operation on HAPS.
