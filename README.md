
# Generating Data Sets to Emulate Dynamic Traffic in a Backbone IP over Optical Network
Siqi Liu, and Zuqing Zhu<br>
School of Information Science and Technology, 
University of Science and Technology of China, Hefei, China
Email: lsq93325@mail.ustc.edu.cn, zqzhu@ieee.org
## Introduction
A backbone IP over optical network usually consists of two layers, i.e., an IP layer and an optical layer. The optical layer is built with a few optical switches interconnected by fiber links. Each optical switch can transparently switch the optical spectrum of a lightpath from an input port to the desired output port. The switches in the IP layer are co-located with the underlying optical switches and connect to them with optical ports, each of which can generate or terminate the optical signal of a lightpath.

To analyze the performance of service provisioning algorithms for an aforementioned multilayer backbone network, one need realistic traffic data sets to emulate the traffic generated in the IP layer. Therefore, the purpose of this technical report is to share our insight and method to accomplish such a task. Moreover, we also attach a data set that consists of 500,000 traffic samples generated with realistic traffic traces.

## Realistic Traffic Traces from the Internet
Note that, in a backbone IP over optical network, a “flow” usually refers to an aggregated one that grooms numerous IP flows between a switch pair in the IP layer. Hence, the traffic on each flow could be highly dynamic, fluctuate with a unique pattern \[1\], and last for a reasonably long period (e.g., tens of hours or even days). Meanwhile, there can be multiple such flows between a switch pair. Therefore, to generate the traffic on a flow, we need to leverage the realistic traffic traces collected on an edge router, which aggregates the traffic from the access networks behind it. Here, the access networks can be those for universities, research institutions, enterprises, or even Internet service providers (ISPs). To this end, we surveyed the related data on the Internet, and found the following proper sources for the realistic traffic traces. Some of the traces share certain similar patterns, but they also have significant difference among each other. We also hope to point out that the traces on these websites are for real-time traffic and will be updated every a few minutes.


|          |                  |          |          |          |
| :--------| :--------------- | :--------| :--------| :--------|
| 1. [SwissiX] | 2. [n-ix] | 3. [lonap]|4. [linx]|5. [cuhk] |
|6. [nyiix-LA] | 7. [nyiix-NY]| 8. [bcix]|9. [ams-ix]|10. [USTC] |


## Characteristics of Traffic Traces
All the realistic traffic traces considered in this report has relatively strong self-similarity. They fluctuate with time and all show daily variation patterns, each of which has peak/off-peak hours in a day. However, how and when each traffic trace reaches its peak/off-peak hours can be unique and change day by day. We will elaborate on their characteristics as follows.


| ID  |  Traffic Pattern | Features |
| :--------| :---------------: | :--------|
|1| ![pat01](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-01.JPG)|1. Peak time: 4:30; <br> 2. Valley time:12:30; <br> 3. Valley / Peak = 0.25; <br> 4. Sharp peak and slow decrease afterwards;<br> 5. URL: [linx]|
|2|![pat02](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-02.JPG)|1. Peak time: around 3:30 am; <br> 2. Off-peak time: around 1:30 pm; <br> 3. Valley-to-peak ratio: 0.4;<br> 4. Peak hours last for around 14 hours; <br> 5. URL: [linx]|
|3|![pat03](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-03.JPG)|1. Peak time: around 5:30 am and 8:30 pm;<br> 2. Off-peak time: around 4:30 pm; <br> 3. Valley-to-peak ratio: 0.04;<br> 4. Bursty traffic with two major peaks in a day;<br> 5. URL: [linx]|
|4|![pat04](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-04.JPG)|1. Peak time: around 10:00 pm;<br> 2. Off-peak time: around 4:30 am; <br> 3. Valley-to-peak ratio: 0.16;<br> 4. From valley to peak, traffic first increases fast and then slowly; from peak to valley, it decreases sharply;<br> 5. URL: [ams-ix-grx]|
|5|![pat05](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-05.JPG)|1. Peak time: around 2:00 pm; <br>2. Off-peak time: around 4:00 am; <br> 3. Valley-to-peak ratio: 0.20;<br> 4. Bursty traffic with major peaks occurring randomly in a day;<br> 5. URL: [ams-ix-nbip]|
|6|![pat06](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-06.JPG)|1. Peak time: around 9:00 am;<br>2. Off-peak time: around 4:00 am; <br> 3. Valley-to-peak ratio: 0.42;<br> 4. Traffic slowly increases for around 18 hours and then decreases sharply for around 6 hours;<br> 5. URL: [ams-ix-ipv6]|
|7|![pat07](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-07.JPG)|1. Peak time: around 2:00 pm;<br>  2. Off-peak time: around 5:00 am; <br> 3. Valley-to-peak ratio: 0.3;<br> 4. Traffic slowly increases for around 17 hours and then decreases sharply for around 7 hours; <br> 5. URL: [SwissiX]|
|8|![pat08](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-08.JPG)|1. Peak time: around 9:00 am; <br> 2. Off-peak time: around 2:00 pm; <br> 3. Valley-to-peak ratio: 0.8; <br> 4. Traffic slowly increases for around 15 hours and then decreases sharply for around 7 hours;<br> 5. URL: [bcix]|
|9|![pat09](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-09.JPG)|1. Peak time: around 4:00 pm; <br> 2. Off-peak time: around 4:00 am; <br> 3. Valley-to-peak ratio: 0.5; <br> 4. Traffic stay steady throughout a day with one valley;<br> 5. URL: [nyiix-NY]|
|10|![pat10](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-10.JPG)|1. Peak time: around 9:00 am; <br> 2. Off-peak time: around 4:00 am; <br> 3. Valley-to-peak ratio: 0.6; <br> 4. Traffic stay steady throughout a day with two minor peaks;<br> 5. URL: [nyiix-LA]|
|11|![pat11](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-11.JPG)|1. Peak time: around 10:00 pm; <br> 2. Off-peak time: around 4:00 am; <br> 3. Valley-to-peak ratio: 0.27; <br> 4. Traffic fluctuates largely throughout a day and stays at a high level for over 17 hours;<br> 5. URL: [cuhk]|
|12|![pat12](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-12.JPG)|1. Peak time: around 9:00 pm; <br> 2. Off-peak time: around 5:00 am; <br> 3. Valley-to-peak ratio: 0.29; <br> 4. When traffic increasing, it stays at a flat level for a while and small spikes happens randomly; <br> 5. URL: [lonap]|
|13|![pat13](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-13.JPG)|1. Peak time: around 10:00 pm; <br> 2. Off-peak time: around 6:00 am; <br> 3. Valley-to-peak ratio: 0.60; <br> 4. Small and sudden increases occur before traffic reaches its valley;<br> 5. URL: [n-ix]|
|14|![pat14](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-14.JPG)|1. Peak time: around 3:00 pm; <br> 2. Off-peak time: around 4:00 am; <br> 3. Valley-to-peak ratio: 0.40; <br> 4. Traffic has three major peaks, which stay close to each other;<br> 5. URL: [USTC]|

## Generate Data Set to Emulate Backbone Traffic
The realistic traffic traces above indicate that the aggregated traffic collected at an edge route experience daily fluctuation, but the fluctuation patterns of the traces may have negative correlation, i.e., the peak time of a trace is the off-peak time of another one, and vice versa. Furthermore, the negative correlation can also be caused by the fact that a backbone network covers multiple time-zones geographically, and traffic flows between different source-destination pairs might have different peak/off-peak hours \[2\]

For the 14 traces mentioned above, we use the following procedure to generate the data set to emulate dynamic traffic on aggregated flows in a backbone IP over optical network.

1.	We preprocess the data of each trace to make sure: 1) the sampling interval is 5 minutes, 2) the value of each sample is normalized such that the peak value of its trace is set to 1, and 3) each trace covers tens of weeks.
2.	For the data set to represent the traffic of an aggregated flow, we randomly choose sample segments from 5 to 10 preprocessed traces, multiple each of them by a random weight in (0, 1), shift the weighted samples in the time domain for \[0, 6\] hours randomly (to emulate traffic from different time-zones), and add the results together and normalize them to obtain a segment of the traffic on an aggregated flow. Then, we repeat the procedure to get the whole traffic data of an aggregated flow, which consists of 50,000 traffic samples.
3.	We repeat Step 2 for 10 times to generate the traffic traces for 10 aggregated flows in a backbone IP over optical network, which includes 500,000 traffic samples in total.

The generated traffic data set is attached, and an example on the generated traffic is shown in the figure below.

## References:

\[1\] S. Bhattacharyya, C. Diot, and J. Jetcheva, “Pop-level and access-link-level traffic dynamics in a Tier-1 POP,” in Proc. of ACM SIGCOMM IMW 2001, pp. 39–53, Nov. 2001.<br>
\[2\] N. Laoutaris, M. Sirivianos, X. Yang, and P. Rodriguez, “Inter-datacenter bulk transfers with netstitcher,” in Proc. of ACM SIGCOMM 2011, pp. 74–85, Aug. 2011.




[SwissiX]: https://www.swissix.ch/infrastructure/traffic
[n-ix]: http://www.n-ix.net/tools/verkehrstatistik/verkehrstatistik-traffic/
[lonap]: https://www.lonap.net/mrtg/lonap-total.html
[linx]: https://portal.linx.net/stats/lans
[cuhk]: http://www.cuhk.edu.hk/hkix/stat/aggt/hkix-aggregate.html
[nyiix-LA]: https://www.nyiix.net/LA-mrtg/sum.html
[nyiix-NY]: https://www.nyiix.net/mrtg/sum.html
[bcix]: https://www.bcix.de/bcix/traffic/
[ams-ix]: https://stats.ams-ix.net/index.html
[ams-ix-grx]: https://stats.ams-ix.net/grx.html
[ams-ix-nbip]: https://stats.ams-ix.net/nbip.html
[ams-ix-ipv6]: https://stats.ams-ix.net/sflow/index.html
[USTC]: http://202.38.64.40/cgi-bin/mrtg-rrd-1000g.cgi/
[Paper]: https://dl.acm.org/citation.cfm?id=505209
[1]: https://dl.acm.org/citation.cfm?id=2018446
