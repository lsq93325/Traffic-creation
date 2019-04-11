# Ingredient


Traffics in backbone network are different from single flows in LAN. Aggregated flows in backbone network show some specific patterns. In backbone network, an edge router may have several access links. Each link serves institutions like school and enterprise or even an ISP.
This means the flow entering backbone network are aggregation of massive connections.The traffic pattern of each flow is also determined by the behavior of access link users.

Based on this fact, we believe traffic fluctuations in backbone network are not totally random and can be predicted. Note that a flow in backbone network is a mixture of small flows aggregated by access link. Thus for one single backbone edge router, the flows coming out of it are different from each other. Thus to emulate the traffic pattern of flow in backbone network, we have to collect sufficient ingredients, i.e., the small flow of access link.

Here, we offer some websites that share traffic statistics of access link:

|          |                  |          |          |          |
| :--------| :--------------- | :--------| :--------| :--------|
| 1. [SwissiX] | 2. [n-ix] | 3. [lonap]|4. [linx]|5. [cuhk] |
|6. [nyiix-LA] | 7. [nyiix-NY]| 8. [bcix]|9. [ams-ix]|10. [USTC] |



These traffic patterns share some similarity, and yet they are different from each other. Next, we discuss the pattern of these traffics. Note that these website will update the statistics every several minutes.

# Characters of Traffic Patterns 
1. Traffic patterns are given in those website. As they claim, the graphs are plotted by averaging the transmitted bits in the past 5 minutes.This gives us fine grained traffic fluctuation.

2. All of the traffic patterns has relatively strong self-similarity. They they fluctuate as time goes by. They all shows daily variation that experiences traffic peak and valley in one day. However, how and when the traffic reach it peak/valley are different from each other.And then we will discuss the features in detial.

| ID  |  Traffic Pattern | Features |
| :--------| :---------------: | :--------|
|1| ![pat01](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-01.JPG)|1. Peak time: 4:30; *counter intuitive*<br> 2. Valley time:12:30; <br> 3. Valley / Peak = 0.25; <br> 4. Sharp peak on a platform around 1.5 Gbps (half the peak) <br> 5. Slightly decrease after the peak hour;<br>6. URL: [linx]|
|2|![pat02](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-02.JPG)|1. Peak time: 3:30; *counter intuitive*<br> 2. Valley time: 13:30; <br> 3. Valley / Peak = 0.4; <br> 4. The peak is not evident since the fluctuation is not fiece; <br> 5. the traffic stay at high level (80% of peak value) for 14 hours;<br>6. URL: [linx]|
|3|![pat03](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-03.JPG)|1. Peak time: 5:30; *counter intuitive*<br> 2. Valley time: 16:30; <br> 3. Valley / Peak = 0.04; <br> 4. There are two peaks in one day, the bigger one at 5:50, the smaller at 20:30; <br> 5. the traffic are bursty, evident spikes occurs anytime;<br>6. URL: [linx]|
|4|![pat04](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-04.JPG)|1. Peak time: 22:00; <br> 2. Valley time: 4:30; <br> 3. Valley / Peak = 0.16; <br> 4. From valley to peak, traffic first increases fast. Then at 10:00 it begins to increase slowly until reach the peak at 22:00; <br> 5. From peak to valley, it decrease sharply;<br>6. URL: [ams-ix-grx]|
|5|![pat05](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-05.JPG)|1. Peak time: 14:00; <br> 2. Valley time: 4:00; <br> 3. Valley / Peak = 0.20; <br> 4. Intensive small spikes are everywhere, while a big spike seems to occur randomly; <br> 5. From peak to valley, it decrease sharply;<br>6. URL: [ams-ix-nbip]|
|6|![pat06](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-06.JPG)|1. Peak time: 21:00; <br> 2. Valley time: 4:00; <br> 3. Valley / Peak = 0.42; <br> 4. Traffic slowly increases for about 18 hours and steeply decreases for about 6 hours; <br> 5. The spike before peak hour makes the traffic experience a small fluctuation;<br>6. URL: [ams-ix-ipv6]|
|7|![pat07](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-07.JPG)|1. Peak time: 14:00; <br> 2. Valley time: 5:00; <br> 3. Valley / Peak = 0.3; <br> 4. Traffic slowly increases the traffic for about 17 hours and steeply decreases for about 7 hours; <br> 5. The traffic first increases to a platform and stays for about 6 hours, then it sharply increases to the peak with in about 3 hours;<br>6. URL: [SwissiX]|
|8|![pat08](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-08.JPG)|1. Peak time: 9:00; <br> 2. Valley time: 14:00; <br> 3. Valley / Peak = 0.8; <br> 4. Traffic almost stay steady throughout a day; <br> 5. There are two peaks in this pattern, but they not so obvious;<br>6. URL: [bcix]|
|9|![pat09](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-09.JPG)|1. Peak time: 16:00; <br> 2. Valley time: 4:00; <br> 3. Valley / Peak = 0.5; <br> 4. Traffic almost stay steady throughout a day; <br> 5. There are one obvious valley and no obvious peak;<br>6. URL: [nyiix-NY]|
|10|![pat10](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-10.JPG)|1. Peak time: 9:00; <br> 2. Valley time: 4:00; <br> 3. Valley / Peak = 0.6; <br> 4. Traffic almost stay steady throughout a day; <br> 5. There are two peaks but the peaks are not obvious;<br>6. URL: [nyiix-LA]|
|11|![pat11](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-11.JPG)|1. Peak time: 22:00; <br> 2. Valley time: 4:00; <br> 3. Valley / Peak = 0.27; <br> 4. Traffic fluctuates within a large range; <br> 5. Traffic stays over 50% of peak value for over 17 hours;<br>6. URL: [cuhk]|
|12|![pat12](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-12.JPG)|1. Peak time: 21:00; <br> 2. Valley time: 5:00; <br> 3. Valley / Peak = 0.29; <br> 4. When trafic increasing, there is a platform and the hight of the platform is about 87% of peak value; <br> 5. There occur "random" samll spike druing the valley and the platform stage;<br>6. URL: [lonap]|
|13|![pat13](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-13.JPG)|1. Peak time: 22:00; <br> 2. Valley time: 6:00; <br> 3. Valley / Peak = 0.60; <br> 4. The traffic rise and fall for three times in a day<br> 5. A small and sundden increase occures before the valley;<br>6. URL: [n-ix]|
|14|![pat14](https://github.com/lsq93325/Traffic-creation/raw/master/image/pattern-14.JPG)|1. Peak time: 15:00; <br> 2. Valley time: 4:00; <br> 3. Valley / Peak = 0.40; <br> 4. The traffic have three main spikes. These spike stay close to each other. This first two experience sudden rises and fall while the last rise and fall slowly ;<br> 5. URL: [USTC]|

# Emulate Flow in Backbone network
Through those patterns we can find that the traffic experience fluctuation everday, but Their charactors are different. Some of them reach their peak at night, while some at noon. Note that, such negative correlation can happen on one backbone link. When it comes to the network spread over several time-zones \[[1]\], the negative correlation will become more severe since the peak hour of different time zones are different. We collect 14 patterns, and considering the negative correlation could happens, we may shift one pattern by several time slots (Here, one slot stands for a 5-min sample) to make it more practical.

Also we consider scale one pattern to another amplitude, which will not affact its traffic feature. Before we composite the emulated backbone traffic pattern, we may expand one traffic pattern in time domain. Specifically, for some traffic patterns performs almost the same for each day of a week, we enlong them by picking traffic of a random day and sticking the traffic right after the orinal pattern. In this way, the pattern will keep it original pattern. As for the patterns that has evidently weekly pattern, we enlong them by picking a random week and sticking the corresponding statistics to the end of original ones.

Thus, we composite the traffic by enlonging the original pattern, shifting their peak hour and adding them together. Specifically,1) each pattern variate at 5-min basis, 2) we enlong them by randomly picking a day pattern or week pattern and appending to the end, 3) we shift them by a random time slot, 4) we add them together. We generate the traffic through the following equation:

![eq1](https://github.com/lsq93325/Traffic-creation/raw/master/image/eq.JPG)

w is randomly selected weight assigned to each trace. shift(trace,s) is the function that cyclic shifts s elements in trace. The specific parameter are listed in the following table:    


|          |           |          |          |          |         |
| :--------| :-------- | :--------| :--------| :--------| :-------|
| W        |         1 |        2 |        3 |        4 |       5 |
| value    |           |          |          |          |         |
| W        |         6 |        7 |        8 |        9 |       10|
| value    |           |          |          |          |         |
| W        |         11|        12|       13 |       14 |         |
| value    |           |          |          |          |         |

|          |           |          |          |          |         |
| :--------| :-------- | :--------| :--------| :--------|:--------|
| s        |         1 |        2 |        3 |        4 |       5 |
| value    |           |          |          |          |         |
| s        |         6 |        7 |        8 |        9 |       10|
| value    |           |          |          |          |         |
| s        |         11|        12|       13 |       14 |         |
| value    |           |          |          |          |         |


The emulated traffic pattern are shown in the following figure:



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
