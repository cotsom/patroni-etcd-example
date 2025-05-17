docker exec -it master psql -c "CREATE TABLE bins  AS SELECT * FROM GENERATE_SERIES(1, 10000) AS id;"

docker exec -it host-slave psql -c "SELECT max(id) from bins;"

docker exec -it h1 docker exec -it pg-h1 bash
patronictl --help

patronictl -c /var/lib/postgresql/patroni.yml list

patronictl -c /var/lib/postgresql/patroni.yml switchover