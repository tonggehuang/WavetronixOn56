# WavetronixOn56
current running wavetronix downloading program on sever .56

### data downloaded from Iowa DOT owned radar sensor and stored in HDFS of INTRANS

Wavetronix is a radar based traffic sensor which collect traffic speed, vehicle counts and sensor time occupancy.
The wavetronix sensors in Iowa are configured to report 20s aggreagated traffic data in XML format in streaming fashion through a web portal.

This program downloads the XML data from the web portal every 20s and parse the XML into line based CSV and append to a new file each day.

This code is currently running on .56 sever at INTRANS and the parsed CSV files are dumped into HDFS everyday for long-term archieve and fast processing. 
