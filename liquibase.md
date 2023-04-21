## How to use liquibase to interact wtih MSSQL database

### Create changelog.sql file

```sql
-- liquibase formatted sql

-- changeset liquibase:1
CREATE TABLE test_table (test_id INT, test_column VARCHAR(255), PRIMARY KEY (test_id))
```

### Use liquibase docker image to run the script against mssql database

```sh
# Get the container IP of MSSQL `docker inspect <containerID> | grep "IPAddress"`
# jdbc:sqlserver://<IP OR HOSTNAME>:1433;database=<DATABASE>

docker run --rm \
-v /Users/sriram/Data/liquibase:/liquibase/changelog liquibase/liquibase \
--url="jdbc:sqlserver://172.17.0.2:1433;database=master;user=sa;password=Welcomme123;trustServerCertificate=true" \
--changeLogFile=changelog.sql update
```

### References
[liquibase-dockerhub](https://hub.docker.com/r/liquibase/liquibase)
[Using Liquibase with MSSQL](https://docs.liquibase.com/start/tutorials/mssql.html?Highlight=connect%20to%20mssql)
