# CYB333-Final-Project
The purpose of this code is to extract file information from a PCAP file. The idea is to capture TCP or UDP file transfers and to be able to pull file type or even the complete file. 
The initial coding took 4 hours to write and was only able to identify a .zip file extension. The issue I was having was identifying individual packets. To overcome this I had to create sessions that looked for packets that contained the same destination and orgin IP and Port numbers in them. This success made it possible to bracket in on a set of packets for a file transfer. If it could not find a packet set it would create a new session and start again to search. Each session was added to a list and I would ask the user which session to parse. The use could input 'all' or the session id.
My next success is able to identify .doc and .exe files. My next goal is to parse more of the packet session out and determine which IP initiated the file transfer. 
I kept getting errors when atempting to nail down which side is the originator. My original focus was trying to pin down which IP came first in the transfer and found that my code was not able to identify it correctly. My next Idea is to work with the file size to identify which point is the origin.
I am able to identify the packets with file payloads in them based on size and have consistently been able to identify the correct sessions about 30% of the time. I am having a hard time identifying the complete file transfer.
Messing around a bit with the logic I generated a file save ability that will attempt to save the information from the packet sessions. It does not identify all of the file extensions. It can do .zip, .exe, and .doc well enough because I was able to identify those extensions before. I also cleaned up some "frustrated" comments. but it does not save the file as the extentions.
Goal: to generate a file extention identification function when saving the file.