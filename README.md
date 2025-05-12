# ee2003-assignment-3-solved
**TO GET THIS SOLUTION VISIT:** [EE2003 # Assignment 3 Solved](https://www.ankitcodinghub.com/product/ee2003-assignment-3-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;90769&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;EE2003 # Assignment 3 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
# Assignment 3

Implement RISC-V ALU instructions

## Goals

– Implement all the instructions in the RISC-V RV32I ISA that correspond to ALU operations.

## Given

– Test bench with test cases having ALU instructions

– Test bench will feed one input instruction per clock cycle

– All registers are assumed initialized to 0 – this should be done in your code

– Template module interface for ALU: **do not** change the ports

– Template module interface for a register file: **do not** change the ports

– Dummy decoder module

## Details on the assignment

For the purpose of this assignment, we are going to implement the ALU as follows:

– Assume the 32-b instruction is read in by a separate module called `dummydecoder` – this module creates a 6-b `opcode` that can be used by the ALU to decide what operation is needed. Since there are a total of &lt; 30 ALU type instructions, 6 bits is ample here.

– The ALU itself should be a combinational module: it does not take a clock input, and only receives the two 32-b values to be operated upon, along with the opcode. It should generate a 32-b output value in a combinational manner.

– The Register File should be capable of generating two outputs in a combinational manner (output appears without waiting for a clock) and taking in one input and writing it into a register (this has to be clocked).

### Dummy Decoder

In practice, you will later design a decoder module that generates most of the control signals for the datapath. Now you can keep it simple and just generate the register select codes, and an `opcode`. This is left as a choice to you.

In principle, you could choose to use a different opcode encoding of more or less than 6 bits, but for this assignment the requirement is to use 6 bits so that it is compatible with the test bench.

**Important**: One more thing the decoder does is to select between the Immediate operand (which would be present in the instruction itself) and one of the register values (`rv2` because of the way the instructions are encoded). Again, in practice, you will have a MUX in the datapath that does this selection. One way to implement it is to send the output of the RegFile back into the decoder, where the selection between this value and the immediate value happens.

### Test cases

The test bench will read inputs from a file, and apply them to the rest of the system one per clock cycle. The inputs will be pure instructions of the ALU type, but they will end up modifying the internal registers. After all the inputs have been applied, the test bench will read back all the inputs from one of the register ports (this is not normally possible, it is done only for testing) and compare them against the expected values.

## HowTo

Fork this repostiry (`EE2003/a3`) into your namespace so that you can edit and push changes.

The `run.sh` script performs all the steps required to compile and test your code. The `iverilog` compiler is used for running the verilog simulations.

**IMPORTANT**: do not rename files or create new files – otherwise the auto-grader will not recognize it. Even if you change the `.drone.yml` file, the system will repeat the tests with different configuration files, and your changes will most likely not be recognized then.

&nbsp;
