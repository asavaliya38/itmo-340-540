# Review Questions

Week-07 Review questions covering Application Layer Protocols and their functions

## Objectives

* Explore and identify the aspects of Application Layer protocols, DNS, HTTP, and SMTP
* Identify how the Application Layer and the Transport Layer interact
* Explain and infer the meaning of packet captures in WireShark

## Questions

1) Consider a TCP connection between Host A and Host B. Suppose that the  TCP segments traveling from Host A to Host B have source port number x  and destination port number y. What are the source and destination port numbers for the segments traveling from Host B to Host A?  
i)The source and destination port numbers for the segments travelling from Host B to Host A: Source port number y and destination port number x.

2) Describe why an application developer might choose to run an application  over UDP rather than TCP.  
i)An application developer might choose UDP over TCP for lower latency, reduced overhead, support for broadcast/multicast, simplicity, and more control over data, but at the cost of reliability and error handling.

3) Suppose a process in Host C has a UDP socket with port number 6789.  Suppose both Host A and Host B each send a UDP segment to Host C with  destination port number 6789. Will both of these segments be directed to the  same socket at Host C? If so, how will the process at Host C know that these  two segments originated from two different hosts?  
i)Yes, For each received segment, at the socket interface, the operating system will provide the process with the IP addresses to determine the origins of the individual segments.

4) True or False (if false correct the statement to be true): Host A is sending Host B a large file over a TCP connection. Assume Host B has no data to send Host A. Host B will not send acknowledgments to Host A because Host B cannot piggyback the acknowledgments on data.  
i)False. Host B will send acknowledgments to Host A independently of any data it has to send.

5) True or False (if false correct the statement to be true): The size of the TCP Window never changes throughout the duration of the connection.  
i)False. The size of the TCP Window can change throughout the duration of a connection. It's a dynamic parameter that can be adjusted based on network conditions and congestion control mechanisms to optimize data transfer.

6) True or False (if false correct the statement to be true): Suppose Host A is sending a large file to Host B over a TCP connection.  If the sequence number for a segment of this connection is m, then the  sequence number for the subsequent segment will necessarily be m + 1.  
i)False. The sequence number for the subsequent segment in a TCP connection is not necessarily m + 1 due to TCP's cumulative acknowledgment mechanism.

7) True or False (if false correct the statement to be true): The TCP segment has a field in its header for Window Size.  
i) True. The TCP segment does indeed have a field in its header for Window Size. This field is used to specify the size of the sender's receive window, which indicates the amount of data that can be sent and buffered by the receiver without acknowledgments.

8) True or False (if false correct the statement to be true): Suppose Host A sends one segment with sequence number 38 and 4  bytes of data over a TCP connection to Host B. In this same segment, the  acknowledgment number is necessarily 42.  
i) False. it may be the case that the segment sent before the segment with sequence number (38-41) got lost. then the acknowledgement number will not be 42.

9) Suppose Host A sends two TCP segments back to back to Host B over a  TCP connection. The first segment has sequence number 90; the second has  sequence number 110. How much data is in the first segment?  
i)Consider sequence numbers,First segment=90
							Second segment=110
							Data in the first segment=110-90
								   =20

 
10) Suppose that the first segment is lost but the second segment, of the previous question, arrives at B. In the acknowledgment that Host B sends to Host A, what will be the acknowledgment number?  
i)Consider the first segment is lost but the second segment arrives at B. In the acknowledgment that Host B sends to Host A, then the acknowledgment number will be first segment of sequence number, that is 90.

11) Fill in the blank: The Transport layer provides reliable communication between two logical hosts over an unreliable network.

## Deliverables

Place your answers to each question next to the *i)*. Copy this template into your own local private repo under the itmo-540 folder. Create a subfolder called: `week-07` and place this document into that folder, push the code to GitHub and submit the URL to this document.

Kurose, James F.; Ross, Keith. Computer Networking (p. 287). Pearson Education. Kindle Edition.
