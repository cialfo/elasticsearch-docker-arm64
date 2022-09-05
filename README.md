# ElasticSearch 6.8 docker image

Built by backporting the 7.12 ARM64 Dockerfile and copying the JDK from the 7.12 ElasticSearch docker distribution for ARM 64 to the 6.8 ElasticSearch distribution in this repo (elasticsearch-6.8.16-SNAPSHOT-linux-aarch64.tar.gz)

# Steps to Configure ElasticSearch 6 using Docker.

# 1. Install Docker
Docker can be installed from [here](https://docs.docker.com/desktop/install/mac-install/)

# 2. Git LFS
It's important to install git-lfs as the image of ES-6 is not a binary file.
```
	git lfs install --skip-smudge

```

# 3. Clone
Please go ahead and clone this repository

# 4. Download the Complete ES 6 Snapshot
```
  cd elasticsearch-docker-arm64
  git lfs pull --include="elasticsearch-6.8.16-SNAPSHOT-linux-aarch64.tar.gz"
```

# 5. Building the image
```
docker build . -t elyalvarado/elasticsearch:6.8
```

# Running the image
You can use Docker for Desktop GUI to run the image or User below command to run it from Terminal

```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" elyalvarado/elasticsearch:6.8
```
