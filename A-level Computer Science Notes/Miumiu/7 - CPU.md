## Control Unit
- Acting as a part of CPU
- **Send the control signal over control bus to handle instructions**
- **fetch, decode and execute instructions**
- **direct the signal to other component, such as I/O devices, ALU and computer memory**

## System Clock


## Register
- PC - Program Counter - Point to the next intruction address to be executed
- MAR - Memory Address Register
- MDR - Memory Data Register
- CIR - Current Instruction Register
- MDR或者CIR里面取出来真正的指令的数据是由两个部分组成的：
	- Opcode + Operand
	- Opcode表示这条指令对应的代码 比如说0010,然后让CU自己去找到底对应的是谁
	- Operand表示这个指令所需要传入的数据 / 参数
	- **Decode阶段说白了就是在看取出来的东西到底对应什么指令**


## Bus 总线传输
- set of parallel wires that allow the transfer data between components in a computer system
- 这里其实意思是同时拥有的wire越多，能一次性传输的数据就越多，从而导致整体数据传输就变得更快 - computer system factor
- Control Bus - Bi-directional 
	- Send the signal from control unit
	- Can ensure that Data Bus or Address Bus wont form a conflict when transmitting
	- 
- Data Bus - Bi-directional
- Address Bus - Uni-directional 单一方向的传输，from CPU to memory and IO devices


## Multi threading
- Can make a processor run multiple tasks on different threads at the same time
- One thread means one task / process running
- 