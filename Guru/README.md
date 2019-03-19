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

## Troubleshoot
In case you want to see if your Guru is able to receive the messages with GELF protocol you can send this message to see if you can see it on the Graylog UI. Run this command on the Guru server:
```
echo -e '{"version": "1.1","host":"example.org","short_message":"Short message","full_message":"Backtrace here\n\nmore stuff","level":1,"_user_id":9001,"_some_info":"foo","_some_env_var":"bar"}\0' | nc -u -w 1 0.0.0.0 12201

```
