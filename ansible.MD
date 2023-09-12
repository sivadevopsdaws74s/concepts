### Ansible
Ansible is a popular configuration management tool now.

**What is configuration???**

Before deploying the application we need to make the server ready. For example
* Installing packages
* Installing Programming languages
* Installing build tools.
* Installing Application Runtime.
* Creation of users, folders, etc.
* Setting permissions.
* Creation of systemctl services.

As a DevOps engineer we need to do this effectively. Basically CRUD over the server.

Creation of configuration --> should be fast and accurate</br>
Update the configuration --> any changes in configuration should be rolled out asap.</br>
Delete the configuration --> delete the configuration if not required.</br>
Read the configuration --> it is easy to read the configuration of server through ansible playbooks.</br>

Earlier we were doing this manually or with shell scripting, but there are few disadvantages with shell script.

1. Shell script is imperative</br>
    We need to provide the sequence of steps to the server. It's syntax is quite complex and sequence based.
2. Shell script is homogenous.</br>
    shell script should be different if the OS distribution is changed.
3. It can't scale to more servers.
4. We need to validate each and every step.

Ansible has following advantages over shell script.
1. Shell script is declarative.</br>
    Declarative means whatever we write we will get with simple syntax. It is ansible responsibility to maintain the state of the server i.e whatever we write Ansible should do that. Ansible syntax is easy.
2. Ansible is heterogenous.</br>
    Ansible can query the node OS distribution and can change the command.
3. Ansible can scale to many servers.</br>
    Ansible can connect with group of servers and configure them.
4. Ansible take care of validation and echo statements to the users.
5. We can re use the code through the feature of roles.

### Pull vs Push configuration

![alt text](images/pullvspush.jpg)

![alt text](images/push.jpg)

**PULL:**
1. Nodes should connect to the servers through agent software.
2. Nodes should download the configuration periodically, say every 30min.
3. Even there is no change in configuration, agents connect to servers that creates unnecessary traffic and data consumption.

**PUSH:**
1. Unlike pull there is no need of agent installation.
2. Whenever there is a change in configuration, server can push to the nodes directly.
3. Ansible uses SSH authentication to connect to the servers.
