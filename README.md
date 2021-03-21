This is a small project on application of kafka messaging service, visualized in real time using open source javascript library and flask. Geo data collected from geojson.io which marks the coordinates saved in a file to stream using kakfka topic. A visualization of the coordinates visited in a map is demonstated in this exmaple.

Things required to get started apache kafka -  https://kafka.apache.org/quickstart, Python

Install kafka broker, zookeeper using the quick start guide page.
If you are running on localhost make sure to check server properties file inside kafka config. Go with default port numnbers for broker and zookeeper.

kafka broker running on port 9092
zookeeper on port 2181

****************************
zookeeper.properties
****************************
dataDir=/Users/documents/kafka_install/kafka_2.13-2.7.0/data/zookeeper
clientPort=2181

****************************
server.properties
****************************
zookeeper.connect=localhost:2181

****************************
Commands to get started:
****************************

#start zookeeper
bin/zookeeper-server-start.sh config/zookeeper.properties

#start kafka server
bin/kafka-server-start.sh config/server.properties

#create topic
bin/kafka-topics.sh --create --topic test001 --bootstrap-server localhost:9092

#list topics
bin/kafka-topics.sh --bootstrap-server localhost:9092 --list

#start producer 
bin/kafka-console-producer.sh --topic topicname --bootstrap-server localhost:9092

#start consumer
bin/kafka-console-consumer.sh --topic topicname --from-beginning --bootstrap-server localhost:9092

#leaflet.js to setup map
https://leafletjs.com/examples/quick-start/

#setup API token to design map
https://account.mapbox.com/access-tokens/

#get coordinates from map (chicago in this example)
http://geojson.io/#map=15/41.8782/-87.6340 

Steps to execute
1. start kafka servers, producers, consumers
2. run app.py to view web app hosted locally
3. run chi_data.py to start reading coordinates file

<img width="940" alt="sample-image-map-marker" src="https://user-images.githubusercontent.com/42100918/111898981-6804bb00-89f7-11eb-8d3b-e8859d7d114f.png">

<img width="159" alt="Screen Shot 2021-03-21 at 3 55 10 AM" src="https://user-images.githubusercontent.com/42100918/111899250-4c021900-89f9-11eb-85a7-0581152936fc.png">




credits : code & dogs
https://www.youtube.com/channel/UCyXsLg7-8OKM7Cc0dsmntDA
