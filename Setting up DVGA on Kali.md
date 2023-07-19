# Setting up - Damn Vulnerable GraphQL Applicaiton on Kali

## Web app setup

- Download the latest version of kali 
- Install build dependencies:
```bash
sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget
```
- Application currently supports Python-3.9. Install this specific version:
```bash
cd ~/Downloads
wget https://www.python.org/ftp/python/3.9.7/Python-3.9.7.tgz
tar -xf Python-3.9.7.tgz
cd Python-3.9.7
```
- Configure and build Python:
```bash
./configure --enable-optimizations --with-ensurepip=install
make -j$(nproc)
sudo make altinstall
```
- Verify SQLite support:
```bash
python3.9 -c "import sqlite3; print(sqlite3.sqlite_version)"
```
- Clone the github repo:
```bash
cd ~/Documents
git clone https://github.com/dolevf/Damn-Vulnerable-GraphQL-Application.git
cd Damn-Vulnerable-GraphQL-Application
```
- Create virtual environment:
```bash
python3.9 -m venv venv
```
- Activate virtual environment:
```bash
source venv/bin/activate
```
- Install project dependencies:
```bash
pip install -r requirements.txt
```
- Run the application using:
```bash
python app.py
```

## GraphQL tools

### Altair GraphQL client
- Visit https://altairgraphql.dev/#download and install the browser extension

### Clairvoyance
- Clone the github repo from: https://github.com/nikitastupin/clairvoyance.git
- This tool supports Python-3.11
- We can simply run this tool using: 
```bash
cd clairvoyance
python -m clairvoyance -h
```

### CrackQL
- Clone the github repo from: https://github.com/nicholasaleks/CrackQL.git
- Setup python3.9 virtual environment and install the requirements
- Run the app using:
```bash
python CrackQL.py -h
```

### commix
- Is an open source project written in python. It attempts to find and exploit command injection vulnerabilies in an automated fashion by fuzzing various parts of HTTP request. 