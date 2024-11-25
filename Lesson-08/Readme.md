## How to Remove Dangling Containers

### As you've already seen, containers that have been stopped or killed remain in the system. These dangling containers can take up space or can conflict with newer containers.

### In order to remove a stopped container you can use the container rm command. The generic syntax is as follows:

```
docker container rm <container identifier>
```

### To find out which containers are not running, use the container ls --all command and look for containers with Exited status.

### You can also remove multiple containers at once by passing their identifiers one after another separated by spaces. Or, instead of removing individual containers, if you want to remove all dangling containers at one go, you can use the container prune command.

### There is also the --rm option for the container run and container start commands which indicates that you want the containers removed as soon as they're stopped.

## How to Run a Container in Interactive Mode

### So far you've only run containers created from either the hello-world image or the fhsinchy/hello-dock image. These images are made for executing simple programs that are not interactive.

### Well, all images are not that simple. Images can encapsulate an entire Linux distribution inside them.

### Popular distributions such as Ubuntu, Fedora, and Debian all have official Docker images available in the hub. Programming languages such as python, php, go or run-times like node and deno all have their official images.

### As an example, if you run a container using the ubuntu image by executing docker container run ubuntu you'll see nothing happens. But if you execute the same command with the -it option, you should land directly on bash inside the Ubuntu container.

```
docker container run --rm -it ubuntu
```

### The -it option sets the stage for you to interact with any interactive program inside a container. This option is actually combination of two separate options.

- The -i or --interactive option connects you to the input stream of the container, so that you can send inputs to bash.

- The -t or --tty option makes sure that you get some good formatting and a native terminal-like experience by allocating a pseudo-tty.

## How to Work With Executable Images

### Take for example my rmbyext project. This is a simple Python script capable of recursively deleting files of given extensions. To learn more about the project, you can checkout the repository:

<!-- https://github.com/fhsinchy/rmbyext -->

### If you have both Git and Python installed, you can install this script by executing the following command:

```
pip install git+https://github.com/fhsinchy/rmbyext.git#egg=rmbyext
```

### Assuming Python has been set up properly on your system, the script should be available anywhere through the terminal. The generic syntax for using this script is as follows:

```
rmbyext <file extension>
```

### To test it out, open up your terminal inside an empty directory and create some files in it with different extensions. You can use the touch command to do so. Now, I have a directory on my computer with the following files:

```
touch a.pdf b.pdf c.txt d.pdf e.txt
```

```
# a.pdf  b.pdf  c.txt  d.pdf  e.txt
```

### To delete all the pdf files from this directory, you can execute the following command:

```
rmbyext pdf

# Removing: PDF
# b.pdf
# a.pdf
# d.pdf
```
