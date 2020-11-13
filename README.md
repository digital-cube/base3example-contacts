[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Python v3](https://img.shields.io/pypi/pyversions/Django.svg)](https://www.python.org/download/releases/3.0/)

# **BASE3 Example - Simple Contacts service**

* Version 3.0.0
* [Base](https://base3.dev/)
* [PyPi](https://pypi.org/project/base3/)
* [DigitalCube](https://digitalcube.rs/)

### Installation

### 1) Checkout code and submodules

```bash
    git clone https://github.com/digital-cube/base3example-contacts.git
    cd base3example-contacts
    git submodule update --init --recursive
```

### 2) Create keys in users service

```bash
    cd users/keys
    ssh-keygen -t rsa -b 1024 -m PEM -f jwt.private_key
    openssl rsa -in jwt.private_key -pubout -outform PEM -out jwt.public_key
    rm jwt.private_key.pub
    cd ../..
```

### 3) Run application in docker 

```bash
    docker-compose up
```

### 4) Run application test locally

To run services and test locally, you need to have installed postgres sql
database and redis.

In postgres create user demo, and the following databases:
demo, test_demo, demo_contacts, test_demo_contacts, demo_users and test_demo_users


```bash
cd users
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt

cd ../mailer
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt

cd ../contacts
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt

cd ..
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt

#run tests
./alltests.sh

#start monolith version of app
./.venv/bin/python app.py 
```

