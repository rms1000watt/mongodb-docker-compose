# MongoDB Docker Compose

## Introduction

MongoDB cluster in Docker Compose

## Contents

- [Usage](#usage)

## Usage

```bash
docker ps -a | cut -d' ' -f1 | grep -v CONTAINER | xargs docker stop -t 1 | xargs docker rm
rm -rf ./data ||:
docker-compose up -d

ansible-galaxy collection install community.mongodb
python3 -m pip install pymongo
ansible-playbook ansible/new-cluster.yml -e "ansible_python_interpreter=$HOME/.asdf/shims/python3"

docker-compose down -t 1
docker ps -a | cut -d' ' -f1 | grep -v CONTAINER | xargs docker stop -t 1 | xargs docker rm
```
