# Digital Signature
- **authentication**, **non-repudiation**, data **integrity**, **confidentiality**
- Hashing algorithm
	- Random File Access
	- Digest Calculation
- Digest is a value calculated from hashing the data to be sent
	- Sent to asymmetric algorithm to become Digitial Signature
- Documents with digitial signature is being sent
- When the receivers receives the data
	- Using receiver's private key to get the document and digital signature
	- digital signature -> digest   by sender's public key
- Then calcluate the document digest with the sent digest
	- if same, not be altered and vice versa

- 
- Digest Why?
	- Source Authenticity - Asymmetric Encryption



## Asymmetric Encryption
- How to identify?
	- Using different keys to decrypt
	- Private keys held by two sides of senders and receivers to decrypt
	- Public key is used to encrypt the data


## Virtual Memory & Swap Memory
- Paging
- **Disk Thrashing** - produced by overutilizing swap memory from RAM to ROM - cause performance decrease
- When CPU needs to exceed the memory from RAM,  virtual memory extends the space to ROM so that CPU can access more available memory.
- Only swap the memory data when necessary.
- Virtual memory is created temporarily



## Deep Learning
- Using Artificial Neural Network
- With hidden layers to learn the pattern that behaves like human brains
- and input output layers
- neurons - 神经元
- Deep learning is a specialised form of machine learning.

- Reason / 好处 / 为什么
- Deep learning systems enable machines to process data with a **nonlinear approach.**
- deal with unstructured data
- ![[Pasted image 20241020220041.png]]


## Pipelining
- **The process is divided into 5 stages:**
	- instruction fetch
	- instruction decode
	- operation fetch
	- instruction execute
	- writeback (WB)
- Each subtasks spends one clock cycle
- No two instructions execute on the same subtasks
- **Example**: Second instruction is added in second time cycle, while the first instruction moves to the second subtask.

## OOP
- Instance - 实例
	- String x = "abc";
	- an instantiation of a class - 一个类的实例化
	- 
- inheritance 
	- inherit the functions and attributes from base class
- Polymorphism
	- 