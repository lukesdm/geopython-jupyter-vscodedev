## GeoPython Workshop Jupyter Container: VSCode Dev Container Edition

This is a clone of the Jupyter Container from the [GeoPython Workshop](https://github.com/geopython/geopython-workshop) but with a [VS Code Dev Container](https://code.visualstudio.com/docs/devcontainers/containers) configuration.
It comes with a bunch of common geo-python packages pre-installed, e.g., gdal, shapely, rasterio, pyproj...
* Open this folder in VS Code. It should ask if you want to re-open in a Dev Container environment. Click yes. 
* VS Code will re-open and build the Dev Container. This will take several minutes (it's much quicker after the first time). Once this is done, you should be able to open a terminal, see installed packages with `pip list`, `pip install` any extra packages you need, and create and run Python code, e.g., `python3 my_code/hello.py`.
* You can also start a jupyter server with `./entrypoint.sh`, and connect to existing notebooks from the workshop, or create your own.
* Git and VS Code tools are installed in the container so features like source control, code completion and syntax highlighting should work as usual.

Original readme follows...

--------------------------


## All Jupyter Notebook Assets

Jupyter Notebook is used to run all examples and exercises.
Jupyter is run in Docker with all dependencies installed.

### Build

```bash
./build.sh
```

This should build the Docker Image `geopython/geopython-workshop:latest`.

### Run

Preferably using Docker Compose with Volume Mapping for Notebooks
and Data. See [docker-compose.yml](../docker-compose.yml).

To run standalone from within this directory:

```bash
docker run -it -p 8888:8888 -v $(pwd)/content:/jupyter/content geopython/geopython-workshop:latest
```

This applies Docker volume mapping for the workshop content contained under `content`.

Look into the output logging and paste the URL with the token like:
http://127.0.0.1:8888/?token=e72ed792ff1d9d90058a7b7443f1ff88f3b12384f721dabe
in your browser.
