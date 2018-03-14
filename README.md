## A Kafka app which tests consumer and admin different behavior.

Kafka consumer behaves differently in the following scenario:
* Create topic
* Send some data
* Get latest offset
* Delete topic
* Get latest offset

In case of:
* consumer: the second latest offset is (`TopicPatrition`, 0).
* admin: the second latest offset throws `UnknownTopicOrPartitionException`.
