[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Python v3](https://img.shields.io/pypi/pyversions/Django.svg)](https://www.python.org/download/releases/3.0/)

# **BASE3 Example - Simple Contacts service**

* Version 3.0.0
* [Base](https://base3.dev/)
* [PyPi](https://pypi.org/project/base3/)
* [DigitalCube](https://digitalcube.rs/)

### Installation

```bash
    git clone https://github.com/digital-cube/base3example-contacts.git
    cd base3example-contacts
    git submodule update --init --recursive

    cd users/keys
    ssh-keygen -t rsa -b 1024 -m PEM -f jwt.private_key
    openssl rsa -in jwt.private_key -pubout -outform PEM -out jwt.public_key
    rm jwt.private_key.pub
    cd ../..

    docker-compose up
```
