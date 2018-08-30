To build the container:

```
docker build -t mesa:18.1.7-xenial -f ./Dockerfile-opengl-xenial --build-arg MESA_DEMOS="true" .
```

To run the container:

```
xhost local:root
docker run -ti --rm -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix  mesa:18.1.7-xenial
```

To check the various driver:

```
glxgears -info
GALLIUM_DRIVER="llvmpipe" glxgearx -info
GALLIUM_DRIVER="softpipe" glxgearx -info
GALLIUM_DRIVER="swr" glxgearx -info
```