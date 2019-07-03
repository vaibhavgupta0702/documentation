.. readdocs documentation master file, created by
   sphinx-quickstart on Wed Jul  3 11:24:33 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Kafka Performance Tuning!
=========================

Scaling and Performance Optimization for Apache Kafka Brokers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Partitions and Consumer Groups in a cluster are the key aspects to Scaling
Topics and Partitions
Kafka topics are divided into a number of partitions, which contains messages in an unchangeable sequence. Each message in a partition is assigned and identified by its unique offset. A topic can have multiple partition logs.
More Partitions Lead to Higher Throughput
The number of consumers is equal to the number of partitions. One partition will only be able to handle one consumer. Multiple partitions allow for multiple consumers to read from a topic in parallel, meaning that you will have a more scalable system. With more partitions, you can handle a larger throughput since all consumers can work in parallel.
Do not set up too many partitions
Partitions are the key to Kafka scalability, but that does not mean that you should have too many partitions. We have seen a few customers with way too many partitions which in turn consumes all resources from the server. Each partition in a topic uses a lot of RAM (file descriptors). The load on the CPU will also get higher with more partitions since Kafka needs to keep track of all of the partitions. More than 50 partitions for a topic are rarely recommended good practice.
Keep a good balance between cores and consumers
Each partition in Kafka is single threaded, too many partitions will not reach its full potential if you have a low number of cores on the server. Therefore you need to try to keep a good balance between cores and consumers. You don’t want to have consumers idling, due to fewer cores than consumers.

Lorem Ipsum

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
