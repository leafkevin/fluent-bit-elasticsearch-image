docker build -t fluentbittcp:latest .
docker run -d --name fluentbittcp -p 5170:5170  fluentbittcp:latest

[INPUT]
    Name        tcp
    Listen      0.0.0.0
    Port        5170
    Chunk_Size  32
    Buffer_Size 4096
    Format      json

[OUTPUT]
    Name  stdout
    Match *

[OUTPUT]
    Name          forward
    Match         *
    Host          192.168.1.200
    Port          24224
    tls           Off
    tls.verify    Off