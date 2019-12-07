# Use Docker




- [Installation](#installation)
- [Image Actions](#images-actions)
- [Container Actions](#container-actions)





## <a name="installation">Installation</a>

Command used to verify the installation

```bash
docker info
```





## <a name="images-actions">Image Actions</a>

- [Show image](#show-image)
- [Remove image](#remove-image)
- [Search image](#search-image)


### <a name="#show-image">Show image</a>

Command used to search for a Docker image

```bash
docker images
```

### <a name="#remove-image">Remove image</a>

Command used to removing images -> Delete the installer

Pre-Note : require use the command "images"

```bash
docker rmi <image-id>
```

docker image prune or even docker image prune -a

### <a name="#search-image">Search image</a>

Command used to search for a Docker image

```bash
docker search <name>
```





## <a name="container-actions">Container Actions</a>

- [Show container](#show-container)
- [Start container](#start-container)
- [Stop container](#stop-container)
- [Remove container](#remove-container)
- [Interactive container](#interactive-container)
- [Log container](#log-container)



### <a name="#show-container">Show container</a>

Command used to see our existing containers ("running")

```bash
docker ps
```

Command used to see all our existing containers ("starting" or "stopped")

```bash
docker ps -a
```



## <a name="#start-container">Start container</a>

Command used to restart a container that has been stopped

Note : require use the command "ps"

```bash
docker start <container-id>
```



### <a name="#stop-container">Stop container</a>

Command used to stop our existing containers ("running")

Note : require use the command "ps"

```bash
docker stop <container-id>
```

> This command sends a SIGTERM signal next to the SIGKILL signal after a considered period of time -> Free resources and save the status
>
>You can use the kill command that sends a SIGKILL signal, which means that it may not do well to release resources and store the state,
not recommended for use in production





### <a name="#remove-container">Remove container</a>

Command used to removing or "uninstalling" containers -> NO delete the installer

Pre-Note : require use the command "ps -a"

Check if the container is found

```bash
docker ps -a
```

```bash
docker rm <container-id>
```

Post-Note : require use the command "ps -a" for see it has been removed



### <a name="#intereactive-container">Interactive container</a>

Facilitates entry into a running container



If we see it in the list we will execute the following command 

```bash
docker exec -it <container_id> <shell>

#example
docker exec -it 40f bash
```

You can run anything inside the container

For example :

```bash
docker exec <container_id> node app.js
```



### <a name="#log-container">Log container</a>

Facilitates debugg container 

The history is available even after the container exist 
* The data is stored in a json file buried under /var/lib/docker
* You can get the complete path using the inspect command
* Use rail -f


```bash
docker logs <container_id> 
```

"attach" command : you want to see what is written to stdout in rel time

```bash
docker attach <container_id> 
```

"exec" command 

```bash
docker exec <container_id> cat /var/log/test.log
```



### <a name="#pause-container">Pause container</a>

Facilitates to pause all of the processes inside a container

```bash
docker run -d --name=XXX XXXX /bin/sh -c “while true; do sleep 2; date; done”

docker pause XXX

docker unpause XXX
```



### <a name="#stats-container">Stats container</a>

Facilitates to show top that runs in the container

```bash
docker top <container_id> 
```

### <a name="#inspect-container">Inspect container</a>

Facilitates infomation abour ta container or a in image

```bash
docker top <container_id> 
```