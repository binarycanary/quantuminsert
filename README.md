QUANTUM INSERT
==============

Additional resources related to our blog post **Deep-dive into Quantum Insert**:

http://blog.fox-it.com/2015/04/20/deep-dive-into-quantum-insert/


PCAPS
-----
PCAP data for research and testing purposes can be found here:

[https://github.com/fox-it/quantuminsert/tree/master/pcaps](https://github.com/fox-it/quantuminsert/tree/master/pcaps)

Detection
---------
We made proof of concept detection capabilities for Bro and Snort to detect `QUANTUMINSERT`. Suricata was already capable to detect these kind of attacks. 

For more information:

[https://github.com/fox-it/quantuminsert/tree/master/detection](https://github.com/fox-it/quantuminsert/tree/master/detection)

Tools
-----
The tools that we used to simulate and perform `QUANTUMINSERT` can be found here:

[https://github.com/fox-it/quantuminsert/tree/master/poc](https://github.com/fox-it/quantuminsert/tree/master/poc)

This fork
-----
The point of this fork is to expand fox-it's quantum insert in the following ways:
 - Add parsing logic (and Scapy dependency) to monitor.py - STATUS:IN DEVELOPMENT
 - Add aio_local.py that has the combined functionality of monitor/shoorter - STATUS:IN DEVELOPMENT
 - Expand shooter.py payload functionality to include more of a regex-dict style lookup. This changes the model a little bit though and may need to scrapped if performance takes a dive. Right now monitor does the filtering (based on tcpdump filters etc). The expansion would be to have shooter.py do the filtering of the data payloads rather than monitor, giving us more flexibility with how and what we shoot on. Monitor would act more like a funnel than a true monitor. STATUS: IN DEVELOPMENT
 - Expand shooter.py payload functionality to include a cache of websites (alexa top 10 or something) with BeEF pre-injected and ready to shoot - STATUS:IN DEVELOPMENT

Additional concerns: The hope for adding parsing logic directly to monitor.py is to make it more into a deploayable agent using something like Fabric. However, adding Scapy and parsing logic to monitor may make it too heavy. Will have to benchmark before/after during development.
