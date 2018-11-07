# ReliableDataTransfer
- Class: CEG4400-01 -- Computer Networks and Security
- Semester: Fall 2018
- Instructor: Dr. Bin Wang

## Introduction
A reliable data transfer protocol is critical for sending information over a non-perfect network medium with any certainty that the data sent is the data received. Retransmitting data in the event of network loss or corruption is necessary to ensure data is received in the correct order and without flipped bits.

The purpose of this project is to demonstrate such reliability via two different protocols: Alternating Bit and Go-Back-N. The following is a brief explaination of those protocols.

## Alternating Bit
Also commonly referred to as 'Stop-and-Wait'. Host A sends one packet and waits to receive an acknowledgment from Host B before sending another. Retransmission is triggered by either receiving a negative acknowledgment (NAK) or an expiring timer. In either case, the packet that was corrupted or lost is retransmitted and therefore must be buffered until acknowledgment. This issue must be resolved before the data transfer can progress. This is a very simple reliable data transfer protocol but suffers low channel utilization. The following flow chart is a depiction of how this protocol might be implemented.


### Flow Chart
![Alt text](img/AlternatingBit.png?raw=true "Alternating Bit Flow Chart")


Created using draw.io

## Go-Back-N
Host A does not need to wait for an acknowledgment before sending packets to Host B. Go-Back-N makes use of buffered packets and cumulative acknowledgments. Packets must be buffered at the sender in order to facilitate retransmission. A sliding window dictates how many packets can be transmitted at one time. Once a cumulative acknowledgment is received from the receiver, the sender removes acknowledged packets from the buffer. Similarly to Alternating Bit, retransmission occurs when a timer expires. Contrarily to Alternating Bit, progress can be made up to a certain point if corruption or loss occurs, but this depends on which packet was corrupted or lost. The following flow chart is a depiction of how this protocol might be implemented.

### Flow Chart
![Alt text](img/GoBackN.png?raw=true "Alternating Bit Flow Chart")


Created using draw.io
