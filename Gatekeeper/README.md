# How to Setup Gatekeeper 
The Gatekeeper is the `logspout`. It is run as a container to gather `stdout` and `stderr` of other containers and send it to the `guru`. 
## Requirement
Install docker and docker-compose.
Make sure you have IP of the `Guru`. 

## Run
Make sure you have `GURU_IP` and run:
```
docker run -e ALLOW_TTY=true -d --name="logspout" --volume=/var/run/docker.sock:/var/run/docker.sock 	--publish=127.0.0.1:8000:80 micahhausler/logspout:gelf  gelf://GURU_IP:12201
```

You can see what is sent by running
`curl http://127.0.0.1:8000/logs`