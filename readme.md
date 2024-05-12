# MongoDB Docker Compose

## Introduction

MongoDB cluster in Docker Compose

## Contents

- [Usage](#usage)

## Usage

```bash
rm -rf ./data ||:
docker-compose up -d

docker run -it --rm --network mongo mongo mongosh s1as:27018
# rs.initiate()
# TODO: ansible? or figure out proper config

docker-compose down -t 1
```
