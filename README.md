# PMTiles Conversion Dockerfile

This repository contains a Dockerfile that converts GeoPackages into Protomaps PMTiles. It uses the Lynker Spatial Hydrofabric under OBDL. For more information, visit [Lynker Spatial](https://www.lynker-spatial.com/).

An example style and usage instructions are contained in the `map` folder.

## How to Produce PMTiles

1. **Build the Docker image:**
    ```sh
    docker build -t pmtiles .
    ```

2. **Wait for the process to complete.** This may take a significant amount of time as it downloads and processes the data.

3. **Launch the Docker image in a terminal:**
    ```sh
    docker run --name hfmap --rm -it pmtiles /bin/bash
    ```

4. **Copy the file from the container to your local disk:**
    ```sh
    docker cp hfmap:/mbtiles/merged/merged.pmtiles .
    ```

5. **Serve tiles locally:** Use a tool like [Martin Tiles](https://martin.maplibre.org/) or the PMTiles utility.
