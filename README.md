# HodorFuzzer
Fellow Hodors,

This is a Fuzzer which scans ports at a target web address to look for open web services, and reports its findings to the console. 
It does so by sending HTTP requests to a sequence of ports at the target.

This program was developed using Python 2.7.9, but will likely run with any version of Python in the 2.6+ family.It can either scan all ports (65535) or the ports you specify in a ports.txt file. 

An example ports.txt is provided in this directory. 
The system expects ports to be in the format of one-per-line like this: 
8888 
21 
22 
122

EXAMPLE USAGE: 

WITH WORDLIST: python fuzzer.py -ports ports.txt -target http://so-hodor.org -throttle 20 -timeout 2 

WITHOUT WORDLIST: python fuzzer.py -target http://so-hodor.org -throttle 20 -timeout 2-ports 

The file name in this directory containing the ports you want to try. This is optional, and if you omit this parameter the system will scan all possible ports.

-target The target URL to investigate, in the format: http://so-hodor.org -- remember to omit any trailing slash.
-throttle The target throttle, which is the maximum number of requests to the server that are allowed to occur a 1 second time window. -timeout The timeout period, in seconds, after which we consider an attempt on a target port to have failed.

Each output is fairly self-explanitory. 

The TITLE field is the title tag of any web-pages that are being served on the target at the specified port. The NOTES field shows some further information about the connection attempt, in case this is important or interesting. 


Special thanks to:
- Ndevnull
- invizible_
