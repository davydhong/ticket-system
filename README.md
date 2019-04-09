# ticket-system
ticket system built on orchestrated microservices

## How to start
install dependencies

```npm install```

start show service on port 3001

```pm2 start shows.js -i 2```

start reservation service on port 3002

```pm2 start reservation.js -i 2```

start ticket service (message layer)  on port 3000

```pm2 start api.js -i 2```

- feel free to change the core count

## REST API End Points
| end point | enabled methods | behavior |
| ------ | ------ | ------ |
| :3000/ | GET | returns all shows |
| :3000/reserve | POST | user can reserve X number of tickets for a target show |
| :3001/ | GET | returns all shows |
| :3001/:id | GET | returns a show |
| :3001/hold-seats | PUT | temp seat hold for reservation |
| :3001/release-seats | PUT | release temp seat hold |
| :3002/:id | GET | returns reservation info |
| :3002/cancel | DELETE | delete reservation under given name and showID in payload |