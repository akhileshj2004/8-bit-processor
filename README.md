# 8-bit-processor
##Design and simulate a 2-stage pipelined 8-bit processor 
which executes 1 address format code snippet using 
Direct addressing mode on logisim platform 

##Brief description of the functional specifications of the Processor designed:


1. Processor Architecture:
 - The processor consists of two pipeline stages: Instruction 
Fetch (IF) and Execution (EX).
 - It operates on 8-bit data.
 
2. Instruction Set and Addressing Mode:
 - The processor supports a 1-address format, meaning each 
instruction specifies one operand.
 - Direct addressing mode is employed, indicating that the 
operand's address is directly provided in the instruction.

3. Registers:
 - The processor includes a minimal set of registers, such as 
an Accumulator (ACC) to store intermediate results during 
execution.

4. Instruction Format:
 - The instruction format is designed to accommodate the 1-
address format and direct addressing mode.
 - Example format: `OPCODE ADDRESS`, where OPCODE 
represents the operation code, and ADDRESS represents the 
direct address of the operand.

5. Pipeline Stages:
Instruction Fetch (IF): Fetches the instruction from 
memory.
 - Execution (EX): Executes the instruction, performing the 
specified operation using the data retrieved from the direct 
address.


6. Pipeline Hazard Handling:
 - Address hazards need to be addressed, ensuring that the 
correct operand is available for execution.
 - Possible solutions include stalling the pipeline or 
implementing forwarding mechanisms.

7. Memory Access:
 - The processor interacts with memory to fetch and store 
data. In direct addressing mode, the specified address is used 
to access data directly from memory.

8. Control Unit:
 - The control unit manages the flow of instructions through 
the pipeline, controls the execution of operations, and handles 
any required data transfers.

9. Simulation and Testing:
 - The designed processor should be simulated using 
appropriate tools to validate its functionality.
 - Test cases should be created to cover a range of 
instructions, addressing scenarios, and potential edge cases.

10. Performance Considerations:
 - Evaluate the performance of the pipelined processor, 
considering factors such as throughput, cycle time, and any 
potential bottlenecks.
 - Optimize the design iteratively based on simulation results.


