# MongoDB Docker Compose

## Introduction

MongoDB cluster in Docker Compose

## Contents

- [Usage](#usage)

## Usage

```bash
brew install mongodb/brew/mongodb-database-tools

docker ps -a | cut -d' ' -f1 | grep -v CONTAINER | xargs docker stop -t 1 | xargs docker rm
rm -rf ./data ||:
docker-compose up -d

ansible-galaxy collection install community.mongodb
python3 -m pip install pymongo
ansible-playbook ansible/init-cluster.yml -e "ansible_python_interpreter=$HOME/.asdf/shims/python3"

# Connect to rs0
docker run -it --rm --network mongo mongo mongosh rs0as:27018

# Connect to rs1
docker run -it --rm --network mongo mongo mongosh rs1as:27018

# Connect to cfga
docker run -it --rm --network mongo mongo mongosh cfga:27019

# Connect to mongos
docker run -it --rm --network mongo mongo mongosh mongos:27017

# Create DB & sharded Collection on hashed _id
# use mydb;
# db.createCollection("mycol");
# sh.shardCollection("db.mycol", { _id: "hashed" });

# Load in data

# Use the DB

# Cleanup
docker-compose down -t 1
docker ps -a | cut -d' ' -f1 | grep -v CONTAINER | xargs docker stop -t 1 | xargs docker rm
```
