class: center, middle, blue

# psadmin.io Cloud Ops

???

* Announcing psadmin.io Cloud Operations, or ioCloudOps
* We have been building our own preferred toolset and methodology for a modern PeopleSoft deployment

---
class: center, white

# OLD

![:img excited, 90%](images/ol-reliable.jpg)

???

* Old reliable methods of PSA
* Tools that have been around like DPK, our DPK bolt-ons built with puppet, psa

---
class: center, white

# NEW

![:img excited, 85%](images/excited.jpg)

???

* New methodologies, using a Cloud first approach
* Leverage cloud APIs and tooling
* New tooling, using terraform, OCI Resource Manager, OCI SDK with python, etc
    * Cloud Manager
    * DPK, psadmin.io Puppet modules
    * `psadmin-plus`
    * `ioco`

---

# ioco
## psadmin.io Cloud Operations Utility

A python utility for common tasks related to administering PeopleSoft in the Cloud

[github.com/psadmin-io/ioco](https://github.com/psadmin-io/ioco)

---

# ioco --help
```
psadmin.io cloud operations utility

usage:
    ioco dpk deploy [options]
                    [--setup-file-system]
                    [--install-packages]
                    [--get-dpk]
                    [--setup-dpk]
                    [--firewall-pia]
                    [--dpk-source=<type> --dpk-platform=<type> --dpk-type=<type>]
                    [--dpk-version=<nbr> --dpk-patch=<nbr>]
    ioco dpk undeploy [options]
    ioco oci block [options]
                   [--make-file-system]
                   [--mount]
                   [--block-path=<path>]
                   [--block-disk=<path>]
    ioco cm attach-dpk-files --nfs-host=<host>
                             --export=<export>
                             [options]
                             [--mount-path=<path>]
...
```

---

# Examples

* `ioco oci block --make-file-system --mount`
* `ioco cm attach-dpk-files`
* `ioco dpk deploy --dpk-type=FSCM`

???

* Create a default partition and file system on new block storage, then mount it
* Attach the CM dpk files repo
* Get DPK files from CM dpk files repo, then deploy a midtier setup

---

# Install

## GitHub
```bash
$ pip install docopt requests
$ git clone https://github.com/psadmin-io/ioco.git
$ cd ioco
$ python -m ioco --help
```
## Python Package Index
```bash
$ pip install ioco
$ ioco --help
```

---

class: center, middle, black

# Demo

???

* Use terraform to build an instance
* Include user_data that uses `ioco` to attach storage

---

# psadmin.io Cloud Ops

## Methodology

We do more than just *Lift, Shift, & Leave*

* Align with Agile, DevOps and IaC
* Leverage cloud tools and APIs
* Monitoring and Notifications
* Compartments, Tags, Budget

---
class: arrows, big

# Cloud Success Stories

## Saint Paul Public Schools

* Tools Upgrade
    * OCI-Classic
        * OCI

???

* 2017
    * Started at SPPS, at 8.52
    * Upgraded to 8.55, added some automation, DPK, etc, general cleanup
* 2018
    * Moved Non-Prod to OCI-C
* 2019
    * Moved Non-Prod to OCI
* 2020
    * Moved Prod to OCI

---
class: center, middle, black

# Demo

???

Deploy an instance using the CM repository