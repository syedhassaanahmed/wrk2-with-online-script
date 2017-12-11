# wrk2-with-online-script
[![Docker Pulls](https://img.shields.io/docker/pulls/syedhassaanahmed/wrk2-with-online-script.svg)](https://hub.docker.com/r/syedhassaanahmed/wrk2-with-online-script/)

Docker image containing [wrk2](https://github.com/giltene/wrk2) with support for online Lua scripts.

## Example usage
```
docker run --rm -it -e "TARGET_URL=https://www.google.com" -e "WRK_HEADER=User-Agent: wrk" -e "SCRIPT_URL=https://<SERVER_URL>/script.lua" -e "WRK_OPTIONS=-t2 -c100 -d30s -R2000 --latency" syedhassaanahmed/wrk2-with-online-script
```
The above runs a benchmark for 30 seconds, using 2 threads, keeping 100 HTTP connections open, and a constant throughput of 2000 requests per second (total, across all connections combined).

## Credits
- **Will Glozer** for creating a modern HTTP benchmarking tool in `wrk`.
- **Gil Tene** for extending `wrk` to support constant throughput load.
- **Ville Rantala** for his [Docker image of wrk with online Lua scripts](https://hub.docker.com/r/vjrantal/wrk-with-online-script/~/dockerfile/) as well as an awesome tutorial on [Load testing with Azure Container Instances and wrk](https://blog.vjrantal.net/2017/08/10/load-testing-with-azure-container-instances-and-wrk/).