# java-cli-bloop-sbt-dolt-trigger

## Description
Creates a small database table
called `dog` with an `insert after` trigger.
The trigger function `ins_dog_trigger` calls `sp_rolling_audit`
that remmoves old entries. 


All output normally
seen in a terminal will be in `java-srv/log` which will dump to the screen. The project may seem to hang but the logs from the container must be written to the project this can take up to 3 min.

Compiled and ran from build server `bloop`.

# Build note
Dependencies must be compatable with jdk8 or less.

## Tech stack
- bloop
- java
- bloop-sbt
  - log4j
  - dolt driver

## Docker stack
- dolthub/dolt-sql-serverdb:latest
- hseeberger/scala-bloop-sbt:11.0.2-oraclelinux7_1.3.5_2.12.10

## To run
`sudo ./install.sh -u`
Creates java-srv/log

## To stop
`sudo ./install.sh -d`
Removes java-srv/log

## For help
`sudo ./install.sh -h`
