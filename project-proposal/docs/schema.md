# Schema Information

## users
column name     | data type | details
----------------|-----------|-----------------------
id              | integer   | not null, primary key
email           | string    | not null, unique
password_digest | string    | not null
session_token   | string    | not null, unique

## tournaments
column name  | data type | details
-------------|-----------|-----------------------
id           | integer   | not null, primary key
author_id    | integer   | not null, foreign key (references users)
title        | string    | not null
description  | text      |

## teams
column name | data type | details
------------|-----------|-----------------------
id          | integer   | not null, primary key
owner_id    | integer   | not null, foreign key (references users)
name        | string    | not null
description | text      |

## registrations
column name    | data type | details
---------------|-----------|-----------------------
id             | integer   | not null, primary key
tournament_id  | integer   | not null, foreign key (references tournaments)
team_id        | integer   | not null, foreign key (references teams)

## team_memberships
column name    | data type | details
---------------|-----------|-----------------------
id             | integer   | not null, primary key
team_id        | integer   | not null, foreign key (references teams)
user_id        | integer   | not null, foreign key (references users)

## follows
column name    | data type | details
---------------|-----------|-----------------------
id             | integer   | not null, primary key
tournament_id  | integer   | not null, foreign key (references tournaments)
follower_id    | integer   | not null, foreign key (references users)

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
