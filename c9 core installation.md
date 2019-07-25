# Install
0. NodeJS is installed previously, [or not](./nodejs%20global%20installation.md)
1. Go root
```bash
sudo su
```
2. Install packets, absence of which make you cry in debugging of installation) 
```bash
apt install gcc g++ tmux git nano
```
3. Clone repo and install
```bash
git clone https://github.com/c9/core.git /var/c9sdk
cd /var/c9sdk
git fetch origin && git reset origin/HEAD --hard
scripts/install-sdk.sh
mkdir /home/workspace
```

# Run

```bash
cd /var/c9sdk
node server.js -w <starting_directory_path> -a <login>:<password> -l 0.0.0.0 -p 5050
node server.js -w /home/workspace -a : -l 0.0.0.0 -p 80
```

# Forever config

```nano forever.json```

```json
{
  "uid": "c9",
  "append": true,
  "watch": false,
  "script": "server.js",
  "sourceDir": "/var/c9sdk",
  "args": [ "-w", "/home/workspace", "-a", "poccomaxa:axamoccop", "-l", "0.0.0.0", "-p", "80" ]
}
```
