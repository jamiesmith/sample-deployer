
# ToDoMap Demo App

A simple NodeJS ToDo app with a twist - it can show you the source and type of provider serving the underlying REST API.

## Deploying on Apcera

To get your own Todo App running on Apcera, click the button below:

[![Deploy](button.png)](http://deploy-to-apcera.jamie.smith.sandbox.demo.proveapcera.io/?template=https://github.com/jamiesmith/sample-deployer)

Fill out the form, and you should be good to go in a few seconds.


## Configuration

There is 'config.json' that maps IP addresses to implied cloud provider, region, map marker and map marker position.

## Local Deployment

Assuming you have a local MongoDb

%cp dot.env .env
%npm install
%npm start

You can edit .env to set up POSTGRES_URI and MYSQL_URI if required.

# Usage

## Database Binding

Supports Postgres, MySql and Mongo.

If env variables for none are present then an In Memory record of the To Dos is kept - clearly only useful in a single instance situation and as a starting point 

If *in-memory* is used a warning alert is placed in the UI to remind you that there is no persistence.

## Cluster Locations
There is a cluster location map which shows the locations defined by the cluster.  This map relies on the config.json file, and looks for tags based on the "datacenter" tag.  The current IP is used to determine which cluster you are in, then shows the other nodes from that cluster.

![Sample Cluster Locations](./prove-cluster.jpg)

The server map section of the page has also been updated to do this.  The map stays where it is, and the active node jumps around while running, while nodes are present.



-----

[deploy from localhost](http://localhost:3000/?template=https://github.com/jamiesmith/sample-deployer)