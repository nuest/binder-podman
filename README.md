# Install podman in Binder

[`podman`](https://podman.io) _in_ a Binder.

`Dockerfile` first version generated with repo2docker, then copied over Conda-stuff from r2d and adjusted paths in the Dockerfile (also `COPY .` instead of `COPY src/`).

```
repo2docker --debug .
```

Start a terminal, then try out podman:

```bash
daniel@1b64d06736bd:~$ podman --version
podman version 1.4.4
daniel@1b64d06736bd:~$ podman run docker.io/rocker/r-base
cannot clone: Operation not permitted
Error: could not get runtime: cannot re-exec process
daniel@1b64d06736bd:~$ podman run nginx
cannot clone: Operation not permitted
Error: could not get runtime: cannot re-exec process
daniel@1b64d06736bd:~$
```

**The process is not allowed to fork!**

## License

Copyright 2019 Daniel Nüst. Published under BSD 3-Clause License.