## Digital Signature
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