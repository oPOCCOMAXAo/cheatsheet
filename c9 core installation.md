#Install

```
sudo su
apt install gcc
git clone https://github.com/c9/core.git c9
cd c9
git reset --hard
scripts/install-sdk.sh
```

#Run

```
node server.js -w <starting_directory_path> -a : -l 0.0.0.0 -p 5050
node server.js -w /home/nodejs/workspace -a : -l 0.0.0.0 -p 8081
```
#Forever config
```
{
  "uid": "c9",
  "append": true,
  "watch": false,
  "script": "server.js",
  "sourceDir": "/home/nodejs/c9",
  "args": [ "-w", "/home/nodejs/workspace", "-a", ":", "-l", "0.0.0.0", "-p", "8081" ]
}
```
