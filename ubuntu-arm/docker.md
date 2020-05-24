# 1. Remove old versions
```
sudo apt-get remove docker docker-engine docker.io containerd runc
```

# 2. Update the apt package index and install packages to allow apt to use a repository over HTTPS
```
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```

# 3. Add Docker’s official GPG key
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

# 4. Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint
```
sudo apt-key fingerprint 0EBFCD88
```

output:
```
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

# 5. Use the following command to set up the stable repository
```
sudo add-apt-repository "deb [arch=arm64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

# 6. Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

# 7. Verify that Docker Engine is installed correctly by running the hello-world image
```
sudo docker run hello-world
```

