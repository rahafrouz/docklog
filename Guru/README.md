# How to Start Guru 
The guru is the garylog server. 
## Requirement
Install docker and docker-compose.
Enter your external IP in the docker compose file. 
Make sure the ports 9000/tcp and 12201/udp are open in your firewall. 
Port 9000 is used for web interface and port 12201 is for GELF to receive log from other machines.

## Run
After modifying `docker-compose.yml` just run it with `docker-compose up -d`. 
You can access it with `your_external_ip:9000`.