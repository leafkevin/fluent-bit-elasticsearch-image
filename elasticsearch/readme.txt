
docker run -d --name elasticsearch --net lognetwork -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:7.9.3
docker run -d --name kibana --net lognetwork -p 5601:5601 kibana:7.9.3