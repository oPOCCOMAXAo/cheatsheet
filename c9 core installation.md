# Install

```bash
sudo su
apt install gcc
git clone https://github.com/c9/core.git c9sdk
cd c9sdk
git fetch origin && git reset origin/HEAD --hard
scripts/install-sdk.sh
```

# Run

```bash
node server.js -w <starting_directory_path> -a <login>:<password> -l 0.0.0.0 -p 5050
node server.js -w /home/nodejs/workspace -a : -l 0.0.0.0 -p 8081
```

# Forever config

```nano forever.json```

```json
{
  "uid": "c9",
  "append": true,
  "watch": false,
  "script": "server.js",
  "sourceDir": "/home/nodejs/c9sdk",
  "args": [ "-w", "/home/nodejs/workspace", "-a", "poccomaxa:1727207", "-l", "0.0.0.0", "-p", "8080" ]
}
```
