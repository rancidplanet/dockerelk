### Docker Compose file for ELK stack single-node deployment
This has only been used on linux.

Few steps before deploying:
1. Filebeat/filebeat.yml will need to be owned and read only by root. This is for security. If this file is changed by an arbitrary user, any file can be read off the file system.
`chown root:root`
`chmod 600 filebeat.yml`
2. maybe theres more steps


To run:
`docker-compose up`

Inspecting errors
`docker-compose ps #list all containers`
`docker logs <containername> #see whats going on in there`
`docker-compose restart <containername>` 


And then view the kibana dashboard on your localhost by visiting
http://localhost:5601


### But wait, where the logs?
Thats what the nginx container is for. Do a quick:
`curl http://localhost:8080`
and `curl http://localhost:8080/testpage404`

There is no test page, but youll get a 404 result in logs
