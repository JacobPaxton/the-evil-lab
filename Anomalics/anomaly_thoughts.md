# Overview
Just thinking through some things involving anomaly detection, especially in regards to cyber incident response.

# Thoughts
Given tabular data, a lot of things are possible. Anomaly in a single column, anomalous row, anomaly from filtered attributes... detection in the data or using the data to train models... visualization, statistical analysis, further lines of inquiry...

But, you'd need to get to tabular data before you can move forward. You can get a head start (before having data) by gaining domain knowledge, but to what end? If you build domain knowledge towards an irrelevant area, you've wasted time. This is not to say that you should do no domain research, this is to say that fundamental knowledge is alright (give it a decent shot), and adapt in the presence of the data.

I've been told, in my position (lacking the data), to present essentially "what is possible with the data" upon receiving it. And so, I shouldn't fret so much about getting that head start. I know for a FACT that the moment I get access to the data that I'm going to go nutzo blitzsano tornado mode on gathering domain knowledge. I shouldn't fear initial contact with "the enemy" because it is indeed initial contact and no amount of preparation ahead of time is going to dodge that fact. 

So, create an anomaly detection environment- and don't mind too much that it may not exactly represent the data you'll soon be working with. 

You can start with Windows, and start with Event Viewer/Sysmon/ETC, and feed that data into Elasticsearch... that's fairly easy. The only difficult part would be finding where those records are stored and copying them into some sort of tabular format. Ingest into Elasticsearch at that point would be trivial, use a docker-compose.yml to launch a Dockerized ELK stack with one `docker-compose up` and run the `elasticsearch.helpers.bulk()` function on your chosen data. 

You can learn to do this on your own, and it *might* help you learn log sources and their contents... study would also net the same. At the end of the day, if you can access the raw records, you can tabularize them and work with them for all sorts of techniques.

Approach the first contact with your chin up- "I'd like to see the data, its schema, its contents, additional sourcing information, how analysts use it and parse it, ..." All of the things you'd hope a researcher would ask when first encountering a new dataset.