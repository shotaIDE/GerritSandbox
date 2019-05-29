# GerritSandbox

## Usage

### Step-1: Prepare env file
Make `.env` file as below to define url of Gerrit server.

```env:.env
HOST_IP=192.168.10.20
```

### Step-2: Copy Gerrit config file
Copy `gerrit.config` file in `volumes/etc/`.

```shell
mkdir -p volumes/etc
cp gerrit.config volumes/etc/
```

### Step-3: Run Gerrit docker init setup from docker
Uncomment in docker-compose.yaml the Gerrit init step entrypoint and run Gerrit with docker-compose in foreground.

```shell
docker-compose up
```

Wait until you see in the output the message Initialized /var/gerrit and then the container will exit.

### Step-4: Start Gerrit in daemon mode
Comment out the gerrit init entrypoint in docker-compose.yaml and start all the docker-compose nodes:

```shell
docker-compose up -d
```

## Backup
Copy `volumes/` directory to backup

## References
- https://gerrit.googlesource.com/docker-gerrit/+/refs/tags/v3.0.0#using-gerrit-in-production
