# SMOP


## General information

SMOP stands for Smart MObility Planner.

The route planning engine is OTP.


## Architecture

SMOP is composed of multiple services:

* Maps : [nextmoov-smop-maps](https://github.com/nextmoov/nextmoov-smop-maps)
* Autocomplete addresses : [nextmoov-smop-autocomplete-addr](https://github.com/nextmoov/nextmoov-smop-autocomplete-addr)
* Autocomplete transit : [nextmoov-smop-autocomplete-transit](https://github.com/nextmoov/nextmoov-smop-autocomplete-transit)
* OTP : [nextmoov-smop-otp](https://github.com/nextmoov/nextmoov-smop-otp)

You can get all the modules by usuing : `git submodule update --init`.

## Launching the modules

To start the system, you need : 

* To provide a OSM PBF file (See hereafter Data sources) in the directory `data` alongside the docker-compose.yml file.

* To provide static GTFS zip files (See hereafter Data sources) in the directory `data` alongside the docker-compose.yml file.

* The provided files needs to be named `xxx-gtfs.zip` (where xxx is only composed of lower case letters).

* Build OTP : `docker-compose run otp-builder ./build`

* Start everything : `docker-compose up`

## Data sources

### Maps

The map data proposed are here : [Geofabriek - Download Belgium](http://download.geofabrik.de/europe/belgium.html)

### GTFS static

The consolidated GTFS file may be provided by [iRail - GTFS](https://gtfs.irail.be/)

### GTFS RT

To have access to the GTFS RT feeds from the providers you can subscribe to thier services :

* [DeLijn](https://data.delijn.be/docs/services/)
* [SNCB / NMBS](https://www.belgiantrain.be/en/3rd-party-services/mobility-service-providers/public-data)
* [STIB / MIVB](https://opendata.stib-mivb.be/)
* TEC is currently working on feed accessible to everyone
