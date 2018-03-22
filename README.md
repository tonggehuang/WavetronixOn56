# WavetronixOn56
current running wavetronix downloading program on sever .56

### data downloaded from Iowa DOT owned radar sensor and stored in HDFS of INTRANS

Wavetronix is a radar based traffic sensor which collect traffic speed, vehicle counts and sensor time occupancy.
The wavetronix sensors in Iowa are configured to report 20s aggreagated traffic data in XML format in streaming fashion through a web portal.

This program downloads the XML data from the web portal every 20s and parse the XML into line based CSV and append to a new file each day.

This code is currently running on .56 sever at INTRANS and the parsed CSV files are dumped into HDFS everyday for long-term archieve and fast processing. 



### The schema of the attributes is as follows:

detectorID, date, startTime, endTime, status, numOfLanes, laneID_1, count, volume, occupancy, speed, smallCount, smallVolume,
mediumCount, mediumVolume, largeCount, largeVolume, (laneID_2, count, volume, occupancy, ......)

Attributes are delimited by "comma". Null means no value applicable, e.g. count&volume are missing for some detectors like this IWZ3065-EB detector, neither for the smallCount, smallVolume etc.

Here is an example:
I-74 NB from North Tower to Isle, 20150829, 232740, 232800, operational, 2, 1,null,null,0,0,null,null,null,null,null,null,2,2,2,6,51,2,2,null,null,null,null

So there are 2 lanes and no vehicles on lane 1, 2 vehicles on lane 2 and they are small vehicles.
