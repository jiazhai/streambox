# streambox

contains usage, Consumer and Producer for docker image: [stream-box](https://hub.docker.com/r/zhaijia/stream-box/)


### how to run docker image

docker command:
```
$ docker run -d \
  --name stream-box \
  -p 9000:9000 \
  -p 8889:8889 \
  -p 6650:6650 \
  -p 8080:8080 \
  -p 8000:8000 \
  zhaijia/stream-box:latest
```


Ports explanation
The image requires several open ports. The table below explains what each port is used for.
```
Component	Port
Heron API Server	9000
Heron UI	8889
Pulsar Broker	6650
Pulsar Admin	8080
Pulsar UI	8000
```

### how to use the docker

Get consumer and producer
```
$wget https://raw.githubusercontent.com/jiazhai/streambox/master/producer.py
$wget https://raw.githubusercontent.com/jiazhai/streambox/master/consumer.py
```

After the docker images running for about 30 seconds, start consumer then producer
```
$python consumer.py
$python producer.py
```

You could also write your own application to use the pulsar and heron server.

### Watch the status topoloy and pular topics
Heron UI:
[http://localhost:8889](http://localhost:8889)

Pulsar topics:
[http://localhost:8000/stats/namespace/sample/standalone/ns1](http://localhost:8000/stats/namespace/sample/standalone/ns1)



