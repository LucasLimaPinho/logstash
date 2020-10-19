# Logstash - [Logstash 7.6.2](https://www.elastic.co/pt/downloads/past-releases/logstash-7-6-2)

#### Introduction

* Logstash is a open source event processing engine part of the Elastic Stack (ELK);
* You configure a pipeline whick is responsible for receiving, processing and shipping events; You can ship logs to Logstash from many sources;
* Logstash can manipulate data too - we can enrich unstructured data with geographical location, filter out what we don't want, etc;
* A Logstash pipeline is essencially a orchestration of plugins -> Pipeline = input + (filter) + output;
* Processed events are sent to Stashes - Stash is a destination like Elasticsearch or Kafka;
* Logstash is horizontable scalable;
* Sending events through Logstash --> **Decoupled Architecture**. Centralized event processing @Logstash; You can remove event processing from your Web Application and centralize in Logstash;
* We can configure a pipeline via command-line using the parameter **-e**. This is the simplest pipeline possible using stdin and stdout as plugins for input and output; In Logstash terminology, stdin and stdout can be called as hashs;

~~~linux

bin/logstash -e "input { stdin { } } output { stdout{ } }"

~~~~

* The same thing can be done with a configuration file **pipeline.conf** written as this:

~~~conf

input {
    stdin {
        
    }
}

output {
    stdout {

    }
}
~~~

So you can start logstash with this command: 

~~~linux

.\bin\logstash -f config\pipelines\pipeline.conf

~~~




