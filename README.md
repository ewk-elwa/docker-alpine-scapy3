# alpine-scapy3

## A compact docker image containing Python3 and the [Scapy](https://pypi.python.org/pypi/scapy-python3/0.21) library

### Usage

Mount your desired script and packet capture into the image's /opt/data directory, then pass the script name and packet capture as arguments.
For example, assuming we have analysis.py and example.pcap in the current working directory, run:
```bash
docker run $(pwd):/opt/data incognitjoe/alpine-scapy3 analysis.py example.pcap
```

My own test scripts were just printing out the DNSRR records from a tiny sample, the script and pcap are in ~/git/test-scapy3, so the command and 
output looks like:
```bash
incognitjoe@dev ~/git/test-scapy3 $ docker run -v $(pwd):/opt/data/ incognitjoe/alpine-scapy3 analysis.py example.pcap
WARNING: Failed to execute tcpdump. Check it is installed and in the PATH
WARNING: No route found for IPv6 destination :: (no default route?). This affects only IPv6
b'dockerhub.com.'
b'dockerhub.com.'
b'hub.docker.com.'
b'hub.docker.com.'
b'fonts.gstatic.com.'
b'fonts.gstatic.com.'
b'secure.gravatar.com.'
b'secure.gravatar.com.'
```

This image is available from [Dockerhub](https://hub.docker.com/r/incognitjoe/alpine-scapy3/).
