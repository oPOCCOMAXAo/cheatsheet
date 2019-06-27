## NodeJS global installation
1. login as root

`sudo su`

2. install packages

`apt install git nano`

3. clone repo

`git clone https://github.com/creationix/nvm.git /opt/nvm`

4. create dir

`mkdir /usr/local/nvm`

5. update `~/.bashrc` with following

```
# enable nvm and nodejs
export NVM_DIR=/usr/local/nvm
source /opt/nvm/nvm.sh
```

6. relogin or use

`source ~/.bashrc`

7. test nvm

`nvm list`

8. install nodejs

`nvm install 12`

9. enable nvm for all users

`nano /etc/profile.d/nvm.sh`

and paste following

```
#!/bin/bash
VERSION=`cat /usr/local/nvm/alias/default`
export PATH="/usr/local/nvm/versions/node/v$VERSION/bin:$PATH"
```

make runnable

`chmod +x /etc/profile.d/nvm.sh`

