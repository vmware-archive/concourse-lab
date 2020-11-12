# concourse-lab is no longer actively maintained by VMware.


# Inastallation:
```
git clone https://github.com/concourse/concourse-docker
./generate-keys.sh
docker-compose up

```

# WebLogin:
```
http://127.0.0.1:8080/
user: test
password: test
```

# Common commands:


## configuring a fly env:
```bash
fly -t local login -c http://127.0.0.1:8080/
```
 
 
## setting a pipeline

Set a pipeline (basic)
```bash
 fly set-pipeline -p my-pipeline -c pipeline.yml
```

Set a pipeline with variables:
```bash
fly -t local set-pipeline -p my-pipeline -c pipeline.yml --load-vars-from secrets.yml
```


## debugging
Check a resource manually:
```bash
fly -t local cr -r my-pipeline/lab-repo
```

Hijack a job:
```bash
fly -t local i -j my-pipeline/build-bbl-image
```


List all containers registered in concourse:
```bash
fly -t local cs
```

Unpausing pipeline
``` bash
 fly -t main unpause-pipeline -p  my-pipeline
 ```
 