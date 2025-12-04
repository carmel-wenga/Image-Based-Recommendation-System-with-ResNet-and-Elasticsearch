# Build an Image Based Recommendation System with ResNet, Elasticsearch and Python

## Requirements
* Python 3.12
* Docker

## Project Setup Instructions
```shell
mkdir etc
python3 -m venv etc/venv
source etc/venv/bin/activate
pip install pip-tools
pip-compile requirements.in
pip install -r requirements.txt
```

## Run Elasticsearch
Use the following command to run Elasticsearch in a Docker container:

```shell
docker run -d --name elasticsearch -p 9200:9200 -e "discovery.type=single-node" -e "xpack.security.enabled=false" elasticsearch:9.1.8
```
The `xpack.security.enabled=false` property disable security for local development. It allows to connect and interact with 
Elasticsearch with http://localhost:9200 without authentication.