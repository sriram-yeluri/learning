
## MSSQL docker image usage

```sh
docker pull mcr.microsoft.com/mssql/server

docker run -d -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=Welcome123" -p 1433:1433 --name mssql mcr.microsoft.com/mssql/server:2022-latest
```

### Connecting to mssql container

```sh
# jdbc:sqlserver://<IP OR HOSTNAME>:1433;database=<DATABASE>
--url="jdbc:sqlserver://172.17.0.2:1433;database=master;user=sa;password=Welcome123;trustServerCertificate=true"
```

### References
https://hub.docker.com/_/microsoft-mssql-server
[Sql Server In Docker](https://github.com/Microsoft/mssql-docker)
