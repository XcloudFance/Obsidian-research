
> [!NOTE] Scenarios
> CSMA/CD is mostly used in Ethernet, Bus topology context.
> 意思就是你看到Ethernet或者Bus topology的情况基本都有

**Ethernet is a wired medium of Local Area Network where all devices connected on the same dedicated line.**

**Can transfer betweeen WANs or LANs**

Using **MAC** **Address** to identify different devices.

data corruption - 数据扰乱 - 本质上就是在讲你数据冲突之后就会把数据搞炸掉

## Bus Topology
- Transmitting data on a dedicated Line  - 专线传输
- Risks to trigger collisions when two devices on the internet **transmit at the same time**
- **Less Privacy**: Other computers can read the data being sent from one to another computer. 
- 

## CSMA/CD  - From Znotes
- **Before transmitting, device checks if channel is busy**
- If busy, device calculates a **random wait time** and waits that time, after which it begins transmission.
- Then during transmission, the device **listens for** other devices also beginning transmission
- **If collision,** transmission is aborted and both devices wait **different random times**, then tried again

## CSMA/CD Drawbacks
- **Inefficiency at high loads**: As network traffic increases, collisions become more frequent, reducing overall efficiency.
- It is possible to happen collisions even after waiting for random time.
- 


