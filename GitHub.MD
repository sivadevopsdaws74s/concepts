### GIT

We should use source code management system for
* Version control
* Track the changes
* Review the changes
* Security and Backup
* Branching
* Collaboration

Git is a popular distributed/decentralized control system.

#### Centralized System Disadvantages
* Single point of failure </br>
    It means centralized systems can't maintain multiple copies. If the central server is down or crashed entire history is gone.
* Limited offline Access </br>
    You should always connect with Internet to push the changes.
* Risk of Data Loss </br>
    If a developer accidentally commits or pushes incorrect or unfinished changes to the central repository, it can affect the entire team's codebase. This makes it crucial to be cautious and vigilant when committing changes.
* Many more </br>
    Branching and working together is very difficult in Centralized systems.


#### Distributed Systems

* Distributed version control system always have local copy in every developer laptop, so the history is preserved everywhere.
* Single laptop is enough when the entire system is crashed including Git server.
* Staging area is there where can selectively send the changes to the central repo. He can send completed changes and keep working on in-progress features.
* Developers can work offline with local repos.

![alt text](images/SVN.png)

### SSH Authentication
1. import the public key in github server
2. create a file called config in .ssh folder inside user directory

follow the below syntax

```
# this is for DAWS-74S
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/sivakumarreddy.pem

#techworldwithsiva
Host github.com-t
  HostName github.com
  User git
  IdentityFile ~/.ssh/techworldwithsiva
```

~ --> /c/Users/user

#### below line tells you are referring to another github account
git remote add origin git@github.com-t:sivadevopsdaws74s/concepts.git