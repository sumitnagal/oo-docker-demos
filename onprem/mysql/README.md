# OverOps OnPrem Example - MySQL
This is a simple example of an OverOps "OnPrem" deployment backed by MySQL.  The `docker-compose.yml` contains the following services:
* `db` - the MySQL server instance
* `db-ui` - an instance of phpMyAdmin to browse MySQL
* `server` - the OverOps backend server, supporting OverOps UI, etc
* `collector` - an OverOps Collector running in a dedicated container (aka Remote Collector)
* `agent` - an OverOps Agent and sample event generator app

## Getting Started
To begin, you must first create a `overops-key.env` file and place it in the same directory as the `Dockerfile`.  Below is a sample `overops-key.env` file.  The sample `TAKIPI_SECRET_KEY` included below is a valid, limited trial key.

### overops-key.env
```properties
TAKIPI_SECRET_KEY=S1#qrXOZTWZsAzN2X0x#02G06kYSRWvet5HQJcq+LVAALN/a8Vu4QqKGIr/d+Ho=#84ae
```

## Docker Compose

### Start the Containers
```bash
docker-compose up
```

### Stop and Destroy the Containers
```bash
docker-compose down
```

## Docker Images
* OnPrem Server - [timveil/oo-docker-onprem-server](https://hub.docker.com/r/timveil/oo-docker-onprem-server/)
* OnPrem Collector - [timveil/oo-docker-onprem-collector](https://hub.docker.com/r/timveil/oo-docker-onprem-collector/)
* Agent - [timveil/oo-docker-agent](https://hub.docker.com/r/timveil/oo-docker-agent/)

## Logging In to the OnPrem Server
Once the server is up, you can access the OverOps UI by going to `http://localhost:8080/login.html`. 

The default username and password are as follows: 

|  Field | Value  |
| ------------- | ------------- |
| Username | `admin@takipi.com` |
| Password | `123456` |


## Database Access
You can browse the OverOps Server databases using phpMyAdmin which can be accessed at `http://localhost:8082`.

### Stats Database
```
takipi
```

### Queue Database
```
qsql
```

### Primitive Data Store (Not Active)
```
pds
```

### Dynalite Databases
```
dynalite
```