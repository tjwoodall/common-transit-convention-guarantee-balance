
# common-transit-convention-guarantee-balance

The public Common Transit Convention Guarantee Balance API with which users can submit requests to query their transit guarantee balance.

### Running

##### To run this Service you will need:

1) [Service Manager](https://github.com/hmrc/service-manager) installed
2) [SBT](https://www.scala-sbt.org) Version `>=1.x` installed
3) [MongoDB](https://www.mongodb.com/) version `>=4.0` installed and running on port 27017 as a replica set

The easiest way to run MongoDB for local development is to use [Docker](https://docs.docker.com/get-docker/).

##### To run MongoDB

###### On Linux and Intel macOS
```
> docker run --restart unless-stopped --name mongodb -p 27017:27017 -d percona/percona-server-mongodb:7.0 --replSet rs0
```

###### On Apple Silicon (for example M1 or M2) macOS
```
> docker run --restart unless-stopped --name mongodb -p 27017:27017 -d percona/percona-server-mongodb:7.0-multi --replSet rs0
```

##### To configure MongoDB to run as a replica set

```
> docker exec -it mongodb mongosh --eval "rs.initiate();"
```

#### Starting the application:

Launch the service and all dependencies using `sm2 --start CTC_GUARANTEE_BALANCE_API`.

This application runs on port 10207.

To run with sbt, stop the Service Manager instance of this service using `sm2 --stop COMMON_TRANSIT_CONVENTION_GUARANTEE_BALANCE` before running with `sbt run` from the project folder.

### Testing

Run `./run_all_tests.sh`. This also checks code formatting and does coverage testing.

Use `sbt test it/test` to run only the tests without the additional checks.

### License

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").
