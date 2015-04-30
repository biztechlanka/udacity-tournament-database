# Udacity-Tournament-Database

Udacity-tournament-database is a simple database project completed for Udacity's full-stack [nanodegree program](https://www.udacity.com/nanodegree) program. The project demonstrates the design and use of a PostgreSQL database to manage a [swiss-system tournament](http://en.wikipedia.org/wiki/Swiss-system_tournament), which is a non-elimination tournament system used in certain sport and game competitions.   

## Table of contents

- [Download](#download)
- [Documentation](#documentation)
- [Copyright and license](#copyright-and-license)

## Download

The files for the project, may be [downloaded here](https://github.com/edwardbryant/udacity-tournament-database/archive/master.zip).

### What's included

Within the download you'll find the following files:

```
udacity-tournament-database-master.zip
├── tournament.py
├── tournament.sql
├── tournament_test.py
└── README.md
```

## Documentation

To use the project files to setup a swiss-system tournament, follow the below steps. 

1. Download the project files at [https://github.com/edwardbryant/udacity-tournament-database/archive/master.zip](https://github.com/edwardbryant/udacity-tournament-database/archive/master.zip).

2. Create a PostgreSQL database

```
CREATE DATABASE tournament 

```

3. Setup two database tables. The first table is to track the players in the tournament (this can be used for individual players or teams). The second table is to track matches within the tournament. The create table statements (see below) are also available in the [tournament.sql]() file 

```
CREATE TABLE players (
    player_id SERIAL primary key, 
    player_name text
    );

CREATE TABLE matches (
    match_id SERIAL primary key, 
    winner SERIAL references players(player_id), 
    loser SERIAL references players(player_id)
    );
```

