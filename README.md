# Nominatim Morocco Docker

[Nominatim](https://github.com/openstreetmap/Nominatim) container optimized for Morocco.

Uses the lastest pbf files from : [http://download.geofabrik.de/africa/morocco-latest.osm.pbf](http://download.geofabrik.de/africa/morocco-latest.osm.pbf) and updates from [http://download.geofabrik.de/africa/morocco-updates](http://download.geofabrik.de/africa/morocco-updates)

# Supported tags and respective `Dockerfile` links #

- [`3.0.1`, `3.0`, `latest`  (*3.0/Dockerfile*)](https://github.com/InteractiveObject/nominatim-morocco-docker/tree/master/3.0)
- [`2.5.1`, `2.5.1`, `latest`  (*2.5.1/Dockerfile*)](https://github.com/InteractiveObject/nominatim-morocco-docker/tree/master/2.5.1)

## Dockerhub
- https://hub.docker.com/r/ioteam/nominatim-morocco-docker/tags/

# Build 

  ```
  docker build -t nominatim-morocco .
  ```

#  Run

  ```
  docker run --restart=always -d -p 8080:8080 --name nominatim-morocco nominatim
  ```
  If this succeeds, open [http://localhost:8080/](http:/localhost:8080) in a web browser

# Running

You can run Docker image from docker hub.

```
docker run --restart=always -d -p 8080:8080 --name nominatim ioteam/nominatim-morocco-docker:latest
```
Service will run on [http://localhost:8080/](http:/localhost:8080)

# Update

Full documentation for Nominatim update available [here](https://github.com/openstreetmap/Nominatim/blob/master/docs/Import-and-Update.md#updates). For a list of other methods see the output of:
  ```
  docker exec -it nominatim sudo -u nominatim ./src/utils/update.php --help
  ```

The following command will keep your database constantly up to date:
  ```
  docker exec -it nominatim sudo -u nominatim ./src/utils/update.php --import-osmosis-all --no-npi
  ```


# User Feedback

**Issues**

If you have any problems or questions about this image, please contact me through a [issue](https://github.com/InteractiveObject/nominatim-morocco-docker/issues)