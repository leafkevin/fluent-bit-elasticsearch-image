docker network create lognetwork
docker build -t fluentbitforward:latest .
docker run -d --name fluentbitforward --net lognetwork -p 24224:24224 -p 24224:24224/udp fluentbitforward:latest

[INPUT]
    Name              forward
    Listen            0.0.0.0
    Port              24224
    Buffer_Chunk_Size 32KB
    Buffer_Max_Size   64KB

[OUTPUT]
    Name  es
    Match *
    Host  elasticsearch
    Port  9200
    Logstash_Format  On
    Logstash_Prefix logs
    Logstash_DateFormat %Y%m%d