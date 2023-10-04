# Setup RabbitMQ

## Install WSL on Windows

Run this command on the PowerShell or the Windows Command Prompt: 

```sh
C:\Users\username> wsl --install
```

The previous command installs an **ubuntu** environment on your PC, for you to have access to various types of command lines, and in this case for you to manage docker containers.

Validate if the installation was succesful by running the following command on any of the previsouly referenced terminals applications:

```sh
C:\Users\username> bash
```

After that you should have a terminal similar to this:

```bash
foo@bash:~$ 
```

If so, you're ready to install docker.


## Install Docker

Please follow Docker official documentation on to install docker in **ubuntu**:

https://docs.docker.com/engine/install/ubuntu/


**Warning**: Do not install the Desktop Docker application! Please use the Apt repository method


## Install and run MQrabbit server

```bash
foo@bash:~$ docker run -d --hostname mqrabbit-host --name sales-orders-mq -p 8080:15672 -p 5672:5672 rabbitmq:3-management
```
**Note**: The **-d** flag stands for detach, it means your docker container will run on the background, so you can close the bash windows it won't stop your container execution

Ports explained:

* **8080:15672** is the port that is going to run the mqrabbit web UI, that we need to manage our queues, exchanges channels and so on


* **5672:5672** is the port for the rabbitmq broker, the one that operates on the queues, it listens, consumes and publishes messages


Now that you have a rabbitmq container running lets move on to the implementation of our first queue. Proceed to the tutorial folder to continue



