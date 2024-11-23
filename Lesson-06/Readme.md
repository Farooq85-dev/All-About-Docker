## Docker Container Manipulation Basics

### In the previous sections, you've learned about the building blocks of Docker and have also run a container using the docker run command.

### In this section, you'll be learning about container manipulation in a lot more detail. Container manipulation is one of the most common task you'll be performing every single day, so having a proper understanding of the various commands is crucial.

### Keep in mind, though, that this is not an exhaustive list of all the commands you can execute on Docker. I'll be talking only about the most common ones. Anytime you want to learn more about the available commands, just visit the official reference for the Docker command-line.

## How to Run a Container

### Previously you've used docker run to create and start a container using the hello-world image. The generic syntax for this command is as follows:

```
docker run <image name>
```

## How to Publish a Port

### Containers are isolated environments. Your host system doesn't know anything about what's going on inside a container. Hence, applications running inside a container remain inaccessible from the outside.

### To allow access from outside of a container, you must publish the appropriate port inside the container to a port on your local network. The common syntax for the --publish or -p option is as follows:

```
--publish <host port>:<container port>
```

### When you wrote --publish 8080:80 in the previous sub-section, it meant any request sent to port 8080 of your host system will be forwarded to port 80 inside the container‌.

### Now to access the application on your browser, visit

```
http://127.0.0.1:8080
```

### You can stop the container by simply hitting the ctrl + c key combination while the terminal window is in focus or closing off the terminal window completely.

## How to Use Detached Mode

### Another very popular option of the run command is the --detach or -d option. In the example above, in order for the container to keep running, you had to keep the terminal window open. Closing the terminal window also stopped the running container.

### This is because, by default, containers run in the foreground and attach themselves to the terminal like any other normal program invoked from the terminal.

### In order to override this behavior and keep a container running in background, you can include the --detach option with the run command as follows:

```
docker container run --detach --publish 8080:80 fhsinchy/hello-dock
```

### The order of the options you provide doesn't really matter. If you put the --publish option before the --detach option, it'll work just the same. One thing that you have to keep in mind in case of the run command is that the image name must come last. If you put anything after the image name then that'll be passed as an argument to the container entry-point (explained in the Executing Commands Inside a Container sub-section) and may result in unexpected situations.

## How to List Containers

### The `container ls` command can be used to list out containers that are currently running. To do so execute following command:

### The container ls command only lists the containers that are currently running on your system. In order to list out the containers that have run in the past you can use the `--all` or `-a` option.

## How to Name or Rename a Container

### By default, every container has two identifiers. They are as follows:

- `CONTAINER ID` - a random 64 character-long string.
- `NAME` - combination of two random words, joined with an underscore.

### Naming a container can be achieved using the --name option. To run another container using the fhsinchy/hello-dock image with the name hello-dock-container you can execute the following command:

```
docker container run --detach --publish 8888:80 --name hello-dock-container fhsinchy/hello-dock
```

### You can even rename old containers using the container rename command. Syntax for the command is as follows:

```
docker container rename <container identifier> <new name>
```

## Note:-

### The command doesn't yield any output but you can verify that the changes have taken place using the container ls command. The rename command works for containers both in running state and stopped state.
