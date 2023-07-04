<h1 align="center">
  GitHub-Metadata
</h1>

## Description
This repository contains a mysqldump  
of a database containing the metadata of 1.000.000+ 
public GitHub repositories.  
The metadata for collected to be used with the tool
[gitAnalyzer](https://github.com/maxvaer/gitAnalyzer).

## Checksum
SHA256 hash of dump.zip:
adaf95dd402ff9d12fae2ff8fb432281377ad8053c7e0da5592f3f949f8e1aab

## Usage
To start a MariaDB using, [this `docker-compose.yaml`](https://github.com/maxvaer/gitAnalyzer/blob/main/docker-compose.yaml)
can be used.   
Be aware, that the folder `mariadb`
need to be created next to the yaml file.   
The credentials for the MariaDB can be found inside the `docker-compose.yaml`.
The container can be started like:
```console
docker-compose up -d
```

To import the dumped data, unzip it:
```console
unzip dump.zip
```
Import using docker:
```console
docker exec -i <mariadb_container_name> mysql -u root -p gitanalyzer < dump.sql
```


