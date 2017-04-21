# docker-baselines

## Overview

This Git project allows a local developer to spin up all local infrastructure needed to run a microservices solution with Postgres, Redis, and RabbitMQ.  This ensures a consistent setup across developers, shared local configurations, and isolation of components from other products that you might be working on.

The following infrastructure will be scaffolded as Containers on your local machine:

| Service | Port | Example Connection String |
| --- | --- | --- |
| Postgres | 49003 | `postgres://postgres@127.0.0.1:49003` |
| Redis | 49002 | `redis://127.0.0.1:49002` |
| RabbitMQ | 49000 | `amqp://127.0.0.1:49000` |
| RabbitMQ Admin | 49001 | `http://127.0.0.1:49001` |

## Prerequisites

* Install [Docker](https://www.docker.com/)

## Instructions

1. Open a Terminal
2. Clone this repo and specify a name for it locally (the folder name is how Docker will name the Containers)
    * e.g. `git clone https://github.com/ericnograles/docker-baselines.git some-product-1`
3. Go to the root of the cloned repo and execute `./start.sh`

## Restarting

1. Open a Terminal
2. Go to the root of the cloned repo
3. Execute `docker-compose restart`

## Recreating

**WARNING**: All persisted data will be destroyed

1. Open a Terminal
2. Go to the root of the cloned repo
3. Execute `docker-compose down`
4. Execute `docker-compose up -d && ./start.sh`
