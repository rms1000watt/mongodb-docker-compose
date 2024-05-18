# MongoDB Docker Compose

## Introduction

MongoDB cluster in Docker Compose

## Contents

- [Usage](#usage)

## Usage

```bash
rm -rf ./data ||:
docker-compose up -d

# ansible-playbook -i ansible/inventory.yml ansible/new-cluster.yml
ansible-galaxy collection install mongodb.mongodb_replicaset # TODO wtf?
ansible-playbook ansible/new-cluster.yml

# docker run -it --rm --network mongo mongo mongosh s1as:27018
# # rs.initiate()
# # TODO: ansible? or figure out proper config

docker-compose down -t 1
```
