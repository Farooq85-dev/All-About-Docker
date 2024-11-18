### Introduction to Containerization and Docker

#### According to International Business Machines Corpooration (IBM),Containerization involves encapsulating or packaging up software code and all its dependencies so that it can run uniformly and consistently on any infrastructure.

#### ‌In other words, containerization lets you bundle up your software along with all its dependencies in a self-contained package so that it can be run without going through a troublesome setup process.

### Consider an Example:-

#### ‌Let's consider a real life scenario here. Assume you have developed an awesome book management application that can store information regarding all the books you own, and can also serve the purpose of a book lending system for your friends.

### ‌If you make a list of the dependencies, that list may look as follows:

- Node.js
- Express.js
- SQLite3

#### Well, theoretically this should be it. But practically there are some other things as well. Turns out Node.js uses a build tool known as node-gyp for building native add-ons. And according to the installation instruction in the official repository, this build tool requires Python 2 or 3 and a proper C/C++ compiler tool-chain.

### Taking all these into account, the final list of dependencies is as follows:

- Node.js
- Express.js
- SQLite3
- Python 2 or 3
- C/C++ tool-chain

#### Installing Python 2 or 3 is pretty straightforward regardless of the platform you're on. Setting up the C/C++ tool-chain is pretty easy on Linux, but on Windows and Mac it's a painful task.

#### On Windows, the C++ build tools package measures at gigabytes and takes quite some time to install. On a Mac, you can either install the gigantic Xcode application or the much smaller Command Line Tools for Xcode package.

#### Regardless of the one you install, it still may break on OS updates. In fact, the problem is so prevalent that there are Installation notes for macOS Catalina available on the official repository.

#### Let's assume that you've gone through all the hassle of setting up the dependencies and have started working on the project. Does that mean you're out of danger now? Of course not.

#### What if you have a teammate who uses Windows while you're using Linux. Now you have to consider the inconsistencies of how these two different operating systems handle paths. Or the fact that popular technologies like nginx are not well optimized to run on Windows. Some technologies like Redis don't even come pre-built for Windows.

#### Even if you get through the entire development phase, what if the person responsible for managing the servers follows the wrong deployment procedure?

### All these issues can be solved if only you could somehow:

1. Develop and run the application inside an isolated environment (known as a container) that matches your final deployment environment.

2)  Put your application inside a single file (known as an image) along with all its dependencies and necessary deployment configurations.

3)  And share that image through a central server (known as a registry) that is accessible by anyone with proper authorization.

#### Your teammates will then be able to download the image from the registry, run the application as it is within an isolated environment free from the platform specific inconsistencies, or even deploy directly on a server, since the image comes with all the proper production configurations.

#### That is the idea behind containerization: putting your applications inside a self-contained package, making it portable and reproducible across various environments.

### Now the question is "What role does Docker play here?"

#### As I've already explained, containerization is an idea that solves a myriad of problems in software development by putting things into boxes.

#### This very idea has quite a few implementations. Docker is such an implementation. It's an open-source containerization platform that allows you to containerize your applications, share them using public or private registries, and also to orchestrate them.

#### Now, Docker is not the only containerization tool on the market, it's just the most popular one. Another containerization engine that I love is called Podman developed by Red Hat. Other tools like Kaniko by Google, rkt by CoreOS are amazing, but they're not ready to be a drop-in replacement for Docker just yet.

#### Also, if you want a history lesson, you may read the amazing A Brief History of Containers: From the 1970s Till Now which covers most of the major turning points for the technology.
