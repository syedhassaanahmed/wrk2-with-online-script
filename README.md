# wrk2-with-online-script
[![Docker Build Status](https://img.shields.io/docker/cloud/build/syedhassaanahmed/wrk2-with-online-script.svg?logo=docker)](https://hub.docker.com/r/syedhassaanahmed/wrk2-with-online-script/builds/) [![MicroBadger Size](https://img.shields.io/microbadger/image-size/syedhassaanahmed/wrk2-with-online-script.svg?logo=docker)](https://hub.docker.com/r/syedhassaanahmed/wrk2-with-online-script/tags/) [![Docker Pulls](https://img.shields.io/docker/pulls/syedhassaanahmed/wrk2-with-online-script.svg?logo=docker)](https://hub.docker.com/r/syedhassaanahmed/wrk2-with-online-script/)

Docker image containing the HTTP benchmaring tool [wrk2](https://github.com/giltene/wrk2) with support for online Lua scripts.

## Example usage
```
docker run --rm -it -e "TARGET_URL=https://www.google.com" -e "WRK_HEADER=User-Agent: wrk" -e "SCRIPT_URL=https://<SERVER_URL>/script.lua" -e "WRK_OPTIONS=-t2 -c100 -d30s -R2000 --latency" syedhassaanahmed/wrk2-with-online-script
```
The above runs a benchmark for 30 seconds, using 2 threads, keeping 100 HTTP connections open, and a constant throughput of ~2000 requests per second (total, across all connections combined). 

Here are some [example Lua scripts](https://github.com/wg/wrk/tree/master/scripts) for generating custom requests.

## Credits
- **Will Glozer** for creating a modern HTTP benchmarking tool in `wrk`.
- **Gil Tene** for extending `wrk` to support constant throughput load.
- **Ville Rantala** for his [Docker image of wrk with online Lua scripts](https://hub.docker.com/r/vjrantal/wrk-with-online-script/~/dockerfile/) as well as an awesome tutorial on [Load testing with Azure Container Instances and wrk](https://blog.vjrantal.net/2017/08/10/load-testing-with-azure-container-instances-and-wrk/).