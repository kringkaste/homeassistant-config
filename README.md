# Home Assistant

## Checkout

Create the folder `~/hassio`. If you want to run this in an other folder you have to update the volumes in the `docker-compose.yml`.

## Add secrets

### Home Assistant

Copy the file `config/secrets.temmplate.yaml` to `config/secrets.yaml` and fill out the missing config options.

### Mosquitto

Create an empty file `config/mosquitto.user`. Then start the setup, MQTT will not work because no device can connect. Then run

``` shell
docker exec -it mqtt mosquitto_passwd /mosquitto/config/mosquitto.user <username> <password>
```

to add new username/passwords to the credential file.

## Start Home Assistant

``` shell
cd ~/hassio
docker-compose up
```

 or in detached:

 ``` shell
cd ~/hassio
docker-compose up -d
```