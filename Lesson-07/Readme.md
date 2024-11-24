## How to Stop or Kill a Running Container

### Containers running in the foreground can be stopped by simply closing the terminal window or hitting `ctrl + c`. Containers running in the background, however, can not be stopped in the same way.

### There are two commands that deal with this task. The first one is the `container stop` command. Generic syntax for the command is as follows:

```
docker container stop <container identifier>
```

### Where `container identifier` can either be the `id` or the `name` of the container.

### I hope that you remember the container you started in the previous section. It's still running in the background. Get the identifier for that container using docker container ls (I'll be using hello-dock-container container for this demo). Now execute the following command to stop the container:

```
docker container stop hello-dock-container
```

### If you use the name as identifier, you'll get the name thrown back to you as output. The stop command shuts down a container gracefully by sending a SIGTERM signal. If the container doesn't stop within a certain period, a SIGKILL signal is sent which shuts down the container immediately.

### In cases where you want to send a SIGKILL signal instead of a SIGTERM signal, you may use the container kill command instead. The container kill command follows the same syntax as the stop command.

### In cases where you want to send a SIGKILL signal instead of a SIGTERM signal, you may use the container kill command instead. The container kill command follows the same syntax as the stop command.

```
docker container kill hello-dock-container-2
```

## How to Restart a Container

### When I say restart I mean two scenarios specifically. They are as follows:

- Restarting a container that has been previously stopped or killed. Like VS_CODE has been closed.

- Rebooting a running container. Like sometimes VS_CODE behave un-expectidely so that we reload our VS_CODE and it works fine. It's just example to actually understand scenario.

### As you've already learned from a previous sub-section, stopped containers remain in your system. If you want you can restart them. The container start command can be used to start any stopped or killed container. The syntax of the command is as follows:

```
docker container start <container identifier>
```

### Now, in scenarios where you would like to reboot a running container you may use the container restart command. The container restart command follows the exact syntax as the container start command.

```
docker container restart hello-dock-container-2
```

### In case of a stopped container, both commands are exactly the same. But in case of a running container, you must use the container restart command.

## How to Create a Container Without Running

### So far in this section, you've started containers using the container run command which is in reality a combination of two separate commands. These commands are as follows:

- `container create` command creates a container from a given image.
- `container start` command starts a container that has been already created.
