# Schema Information

## teams
column name | data type | details
------------|-----------|-----------------------
id          | integer   | not null, primary key
owner_id    | integer   | not null, foreign key (references users)
name        | string    | not null

## tournament_teams
column name    | data type | details
---------------|-----------|-----------------------
id             | integer   | not null, primary key
tournament_id  | integer   | not null, foreign key (references tournaments)
team_id        | integer   | not null, foreign key (references teams)

## followings
column name    | data type | details
---------------|-----------|-----------------------
id             | integer   | not null, primary key
tournament_id  | integer   | not null, foreign key (references tournaments)
follower_id    | integer   | not null, foreign key (references users)

## tournaments
column name  | data type | details
-------------|-----------|-----------------------
id           | integer   | not null, primary key
author_id    | integer   | not null, foreign key (references users)
title        | string    | not null
description  | string    |

## tags
column name | data type | details
------------|-----------|-----------------------
id          | integer   | not null, primary key
label       | string    | not null, unique

## taggings
column name    | data type | details
---------------|-----------|-----------------------
id             | integer   | not null, primary key
tournament_id  | integer   | not null, foreign key (references tournaments)
tag_id         | integer   | not null, foreign key (references tags)

## users
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
email           | string    | not null, unique
password_digest | string    | not null
session_token   | string    | not null, unique
