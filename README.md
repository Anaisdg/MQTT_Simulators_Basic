# MQTT Simulators

This repoistory will allow you to spin up differnt MQTT simulators producing fake IoT data for differnt scenerios. 

## Scenarios

### Emergency Generators (Payload: JSON)
Each generator will write to its own MQTT topic the following values: 

1. Load
2. Voltage
3. Fuel Level
4. Temperature

The payload will look like this:

```json
{"generatorID": "generator1", "lat": 40.68066, "lon": -73.47429, "temperature": 186, "power": 186, "load": 2, "fuel": 277}
```


## Setup

### Docker (Recommended)


1. Clone this repo to your system

```bash
git clone https://github.com/Jayclifford345/mqtt-emergency-generator.git
```

2. Edit the .env file with your InfluxDB v3 credentials. 

3. Build the simulator docker image:

```bash
docker build emergency_generator/. -t emergency-generator:latest
```

4. Deploy the docker-compose file:

```bash
docker-compose up -d
```
