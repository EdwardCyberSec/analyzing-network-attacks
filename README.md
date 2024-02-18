<h1>Analyzing Network Attacks</h1>

<h2>Description</h2>

In this task, I was asked to go through the following scenario and answer two questions in the end: <br />

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. <br />

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.<br />

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. <br />

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees. <br />

Questions to be answered:
1: Identify the type of attack that may have caused this 
network interruption
2: Explain how the attack is causing the website malfunction

<br />

<h2>Resources Used</h2>

- <b>Wireshark TCP_HTTP log</b> 

<h2>Identify the type of attack that may have caused this 
network interruption</h2>
  
One potential explanation for the website's connection timeout error message is a DOS attack.
The logs show that the server stops responding after getting sent to many SYN packets.
This event could be: a type of DOS attack called SYN flooding.

<h2>Explain how the attack is causing the website malfunction</h2>

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:

1. A SYN packet is sent from the source to the destination, requesting to connect.

2. The destination replies to the source with a SYN-ACK packet to accept the connection request. The destination will reserve resources for the source to connect.

3. A final ACK packet is sent from the source to the destination acknowledging the permission to connect.

However, when a malicious actor sends a large number of SYN packets all at once the server is not able to establish a SYN/ACK because of the overloading of SYN packets. Which causes the server to not be able to work as intended.
The logs indicate that it was overloaded and was unable to accept legitimate SYN requests. This affects the server by not allowing anyone who receives a connection timeout error message into the server.
