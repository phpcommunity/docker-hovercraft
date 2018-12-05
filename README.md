# phpcommunity/hovercraft Docker Image

[![Docker Automated Build](https://img.shields.io/docker/automated/phpcommunity/hovercraft.svg?style=flat-square)](https://hub.docker.com/r/phpcommunity/hovercraft/) [![Apache-2.0 License](https://img.shields.io/github/license/phpcommunity/docker-hovercraft.svg?style=flat-square)](https://github.com/phpcommunity/docker-hovercraft/blob/master/LICENSE) [![Docker Build Status](https://img.shields.io/docker/build/phpcommunity/hovercraft.svg?style=flat-square)](https://hub.docker.com/r/phpcommunity/hovercraft/builds/)

This is a basic Docker image for building and locally previewing [Hovercraft](https://github.com/regebro/hovercraft) presentations. The image is available for public use on Docker Hub at [phpcommunity/hovercraft](https://hub.docker.com/r/phpcommunity/hovercraft/).

## Usage

To use this image, run the following command, replacing `/path/to/presentation` with the local path to the root of your Hovercraft presentation and `presentation.rst` with the name of your presentation file within `/path/to/presentation`.

``` bash
docker run -it --rm -p "9000:9000" -v /path/to/presentation:/presentation phpcommunity/hovercraft presentation.rst
```

In a web browser, go to <http://localhost:9000> to view your presentation.

While the container is running, Hovercraft will watch for changes and generate the presentation on each save.

### Generating HTML

You may also use this image to generate HTML that you can share or publish. Using a similar command, provide a path to the directory where you wish the HTML output to be generated. This directory must exist within the `/path/to/presentation` directory, so that the Docker container has permission to write to it. If the path does not exist, Hovercraft will create it.

``` bash
docker run -it --rm -v /path/to/presentation:/presentation phpcommunity/hovercraft presentation.rst my-presentation/
```

You may then open `my-presentation/index.html` in a web browser.

## Docker Image Tags

* `latest` ➜ `2.6` ([hovercraft 2.6][])


[hovercraft 2.6]: https://github.com/regebro/hovercraft/releases/tag/2.6
