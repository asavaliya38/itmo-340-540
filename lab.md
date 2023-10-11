# Lab Week-07 Transport Layer

## Objectives

* Explore and explain the nature of Transport Layer packet structures
* Explore and describe the fields of HTTP packets
* Explore and describe the fields of DNS packets

### Questions

1. Using the Wireshark capture from Blackboard, titled: `failed-dns-query.pcapng` Enter a filter for just `dns` packets. Looking at packet number 430:  in the Application layer, what is the content of the Queries field?  
i)In the DNS query content the DNS name is neverneverclickthis.com, length is (23), Label Count = 2, it is Host A DNS Record and Class IN (0x001)

2. In packet number 431 there is a response.  Under the Flags field, in addition to the Response and 2 Recursion fields being set -- what other flag is set?
i)  Reply Code is set: 0011 (which indicates No Such Name) for the above DNS.

3. What is the outcome of packet 431?  
i)This indicates that there is NO SUCH NAME for this DNS and it was responded by Primary DNS Server which has SOA DNS Record "a.gtld-servers.net" in Info Column of this trace.

4. Look at packet 447, what is the value in the UDP source port field and what is the value of the destination port field?  
i)source port:61833
destination port :53

5. Open the packet capture: `second-http-with-fin.pcapng` Starting with packet 3.  What are the TCP flags set for packet 3,4, and 5. What is this exchange called?  
i)Packet Number 3 it is Syn Flag set and Packet Number 4 flag is set to SYN and ACK, this is called TCP 3 Way handshake exchange to eshtablish a secure and reliable connection.

6. Why does TCP do this?  
i)To eshtablish a secure and reliable connection.

7. Look at Packet 8 and 9 -- what is packet number 9's relationship to 8 (the numerical order is just a coincidence and not the answer)  
i)packet 8 is a request packet and 9 is a response packet so packet 9's to 8 establishing a request-response relationship.

8. Starting in Packet 7, after the 3 way handshake has been established, why is the TCP payload length 0 bytes in size?  
i)In Packet 6 there is Get request for /second.html HTTP/1.1 and Packet 7 is an Acknowlegement to it, which is why it does not contain any payload data.

9. Which TCP flag (or type) is sent back to acknowledge a SYN packet?  
i)Flag type is A, means Acknowledgement.

10. Starting at packet 30-32, what TCP flag is sent to signal the server side to begin to tear down the TCP connection? 
i)In Packet 30, Fin and Ack flag is sent from server to client indicating that the request data has been sent to client "Conversation complete". In Packet 31 Client is has Ack flag to acknowledge that the data has been recieved succesfully and in Packet 32 client has sent Fin and Ack flag to inform the server to initiate the graceful closure of this connection.

11. Using the `TCP-seq-ack-example.xlsx` (Spreadsheet) and using the packet capture `second-http-with-fin.pcapng` -- fill out the columns of the entire http connection, from the initial three way handshake to the the three way tear down handshake. This will show you and end to end connection process for http over TCP to get a simple webpage. Save the modified spreadsheet into your github directory and commit to your repo along with the markdown files.

12. Using the packet capture `complete-tcp-large-image.pcapng`, this retrieves a simple webpage with a single image on it. Yet there are nearly 140 TCP segments captured (along with many ACKs) as part of the transfer of this webpage.  Compare this to the http request in the packet capture `second-http-with-fin.pcapng`, which retrieves a simple webpage with a single image and only has around 30 tcp segments transferred. Can you explain what each packet capture is requesting and why the number of tcp segments are different?  
i)The each packet captures, you can analyze them with packet capture analysis tools to understand the specifics of each request and response,the differences in the number of TCP segments could be due to variations in website design, server configurations, network conditions, and protocol optimizations.

13. Using the packet capture `dns.npcapng` and a **dns** filter, starting from packet number 325 (look up for ucla.edu). Explain the presence or lack there of, a sequence number field in the UDP header.  
i)In UDP, there is typically no sequence number field in the header. UDP is a connectionless protocol, which means it does not provide sequencing or acknowledgment of packets like TCP does. UDP is used for lightweight, fast data transmission where the order of packets is not guaranteed, and there is no handshaking or reliable data delivery mechanism.

14. List the 5 layers used in the network  
i)  1.Application Layer
	2.Transport Layer
	3.Network Layer
	4.Data Link Layer
	5.Physical Layer

## Deliverables

Place your answers to each question next to the *i)*. Copy this template into your own local private repo under the itmo-540 folder. Create a subfolder called: `week-07` and place this document into that folder, push the code to GitHub and submit the URL to this document.
