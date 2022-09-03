# Software Architecture 2022-ii

Repositorio para los laboratorios de la asignatura: Arquitectura de Software 2022 - II, de la Universidad Nacional de Colombia

## Integrantes: 
Integrantes:
- pgrisales [at] unal.edu.co
- hpotosij [at] unal.edu.co
- andiazo [at] unal.edu.co


## Ejecución
Dentro del directorio swarch2022ii_db, ejecutar

``` bash
docker build -t swarch2022ii_db .
docker run -d -t -i -p 3306:3306 --name swarch2022ii_db swarch2022ii_db
docker run --name db_client -d --link swarch2022ii_db:db -p 8081:80 phpmyadmin
```

Dentro del directorio swarch2022ii, ejecutar

``` bash
docker build -t swarch2022ii_ms .
docker run -p 4000:4000 -e DB_HOST=<IP_CONTAINER> -e DB_PORT=3306 -e DB_USER=<DB_USER> -e DB_PASSWORD=<DB_PASSWORD> -e DB_NAME=swarch2022ii_db -e URL=0.0.0.0:4000 swarch2022ii_ms
docker ps
```
