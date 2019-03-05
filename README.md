# bsides-ctf-2019

Forensic challenge zippy

In this challenge a file is given as zippy.pcapng file in which a stream of tcp packet is there. Where tcp packets contain some data.
First of all select a packet which contains some data then we right click on it and select follow > TCP stream where it contains this data 

nc -l -p 4445 > flag.zip
unzip -P supercomplexpassword flag.zip
Archive:  flag.zip
  inflating: flag.txt 
  
then we got idea as zippy.pcapng file contains some set of file.
Then run this command

tcpxtract -f zippy.pcapng
as we get output
Found file of type "zip" in session [192.168.56.2:4244 -> 192.168.56.104:23825], exporting to 00000000.zip

means 00000000.zip file is formed.

then unzip this file using
unzip -P supercomplexpassword flag.zip

we got output as
Archive:  flag.zip
  inflating: flag.txt 
  
cat flag.txt      #we got flag yeah!!!!
CTF{this_flag_is_your_flag}


  
