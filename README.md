# ElasticSearch 6.8 docker image

Built by backporting the 7.12 ARM64 Dockerfile and copying the JDK from the 7.12 ElasticSearch docker distribution for ARM 64 to the 6.8 ElasticSearch distribution in this repo (elasticsearch-6.8.16-SNAPSHOT-linux-aarch64.tar.gz)

# To Directly Run this Use this command
```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" cialfo/elasticsearch:6.8
```

# How to generate Dockerhub Image Content and Push Changes to it.

# 1. Git LFS
It's important to install git-lfs as the image of ES-6 is not a binary file.
```
git lfs install --skip-smudge
```

# 2. Clone
Please go ahead and clone this repository
```
git clone git@github.com:cialfo/elasticsearch-docker-arm64.git
```

# 3. Download the Complete ES 6 Snapshot
```
cd elasticsearch-docker-arm64
git lfs pull --include="elasticsearch-6.8.16-SNAPSHOT-linux-aarch64.tar.gz"
```

# 4. Building the image
```
docker build . -t cialfo/elasticsearch:6.8
```

# 5. Running the image
Use below command to run it from Terminal

```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" cialfo/elasticsearch:6.8
```

# 6. Login To Docker
Use Credentials mentioned in 1Password
```
docker login
```

# 7. To Push Changes, Use this command
```
docker push cialfo/elasticsearch:6.8
```

# You are all set!
Reach out to viral.parekh@cialfo.com.sg / stephan@cialfo.com.sg for any issues
