# WholeTale integration testing with Postman/Newman

Demonstration of [Postman](https://www.getpostman.com/) for API integration testing. This directory contains a Postman collection and environment intended for executing API tests against a running instance of Whole Tale.  Postman can be used interactively or [Newman](https://www.getpostman.com/docs/postman/collection_runs/command_line_integration_with_newman) for command line execution

## Using Postman

Download free [Postman application](https://www.getpostman.com/) for your OS.

### Import the collection

In Postman, select "Import" and browse to this directory. Select ``wholetale.postman_collection.json``. You should now see a collection called "wholetale".

### Import the environment
Select the settings cog next to the environments drop-down then "Manage Environments". Select the "Import" button and browse to this directory. Import "wholetale.postman_environment.json".  You can edit the environment as needed.

### Export the collection
In Postman, select the wholetale collection then select the "Download Collection" link. Select v2.1 format and save the collection to this directory.

### Export the environment
In Postman, select the "wholetale" environment, then the settings cog, then "Manage Environments" and "Download Environment". Save the file to this directory as ``wholetale.postman_environment.json``


### Running tests
Select the test and select "Send".  Note the "Tests" and "Test results" tabs.


## Using Newman
While Newman can be installed via ``npm``, it's probably easiest to use an
official [Docker image](https://hub.docker.com/r/postman/newman_alpine33/).

```
docker run -v `pwd`:/etc/newman -t  postman/newman_alpine33  --insecure --collection=wholetale.postman_collection.json --environment=wholetale.postman_environment.json --delay-request=1000

```
