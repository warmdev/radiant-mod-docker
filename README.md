## Dockerfile for Radiant

Dockerfile for the `Radiant` business analytics tool developed by [Vincent Nijs](https://github.com/vnijs/radiant).

## Dockerfile for `radiant-mod`

Dockerfile for [radiant-mod](https://github.com/warmdev/radiant-mod)

The Dockerfile is inspired by the `rocker/shiny` image and uses the `shiny-server.sh` startup script from https://github.com/rocker-org/shiny.

### Usage

`Radiant` will be live at `http://localhost:3838/radiant/inst/base`. Replace `base` with `quant`, `analytics` or `marketing` for other `Radiant` apps. See https://github.com/vnijs/radiant for details.

```
git clone https://github.com/warmdev/radiant-mod-docker.git
cd radiant-mod-docker
sudo docker build -t radiant-mod .
sudo docker run -d -p 3838:3838 -v {host_data_folder}:/srv/shiny-server/data radiant-mod
```

`Radiant` will be live at `http://localhost:3838/marketing`. 

### FAQ

If you see `n_distinct` and `na.rm` related errors on the visualization page, this is due to older versions of dependencies (especially the `dplyr` package). In this case, force rebuilding the Docker image (by adding or removing a space to line 18) solves the problem.

### Version information

* OS: CentOS 7
* R: Revolution R Open 3.2.2
* Shiny Server: 1.4.0.756
* Radiant: 0.3.17
