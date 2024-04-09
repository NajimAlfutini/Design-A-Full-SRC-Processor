# Design A Full SRC Processor

A SRC (Simple RISC Computer) processor is a type of computer processor that uses a limited number of instructions to perform its tasks. 
RISC processors are widely used in a variety of applications, including embedded systems, mobile devices, and servers. 
They are known for their high performance and low power consumption, making them an attractive choice for many types of systems.

RISC processors are designed to be simple, fast, and efficient, with a focus on executing 
a small set of instructions fast rather than trying to support many complex instructions. 

# Processor specs and design logic (Design Decisions):

## SRC processor has specific specifications, the specs of the SRC that we designed is:
	Our design is a 1-bus system. Which means we use one bus to transmit/share data between the components.
	In every clock we perform one micro-operation.
	It has a 32 general purpose register and each one has size of 32-bit .
	It has a 32-bit program counter (PC) which means it can access 2^32 = 4GB.
	It has a 32-bit instruction register (IR).
	The word is 4 bytes = 32-bit, and only a 4 byte can be fetched or stored into main memory.
	Main memory is organized as an array of bytes.

![image](https://github.com/NajimAlfutini/NajimAlfutiDesign-A-Full-SRC-Processo/assets/138370248/33cd5bb3-4e5b-4611-ac47-cd8a240c2da5)

# 
## The control unit design:
![image](https://github.com/NajimAlfutini/NajimAlfutiDesign-A-Full-SRC-Processo/assets/138370248/785007b3-8948-4ad5-ba35-07092e76868e)

### The control unit contains of four main components:

a.	Clocking logic: The main function of this component is to generate enable signal for the counter in the step generator.
![image](https://github.com/NajimAlfutini/NajimAlfutiDesign-A-Full-SRC-Processo/assets/138370248/91639e9c-a1dc-4acb-9609-e4b80ade1568)

b.	The control step generator: contains of a four-bit up counter and control step decoder which give the wanted step. 
The counter is with load input because if the counter reserve a Goto6 signal must the step generator go to step 6 by load 0110 to counter.
![image](https://github.com/NajimAlfutini/NajimAlfutiDesign-A-Full-SRC-Processo/assets/138370248/842b68a7-2924-4ca8-8eea-a615c826a60a)

c.	Opcode decoder: This decoder will take opcode as input IR<31 …27> and will generate a signal in the wanted instruction.

d.	Control signal encoder: Is the main part in control unit because it contains a Boolean function for each signal. 



