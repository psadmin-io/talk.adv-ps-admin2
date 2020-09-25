class: center, middle, blue

# psadmin-plus

---

# psadmin-plus

* psadmin-plus, or  `psa`, is a psadmin helper script

--
* Great for completing multiple tasks in one command

--
* Open Source

  [github.com/psadmin-io/psadmin-plus](https://github.com/psadmin-io/psadmin-plus)

---

# psa help

```
Usage: psa [command] <type> <domain>

    Commands:
        help           display this help message
        list           list domains
        summary        PS_CFG_HOME summary, no type or domain needed
        status         status of the domain
        start          pooladd, if enabled, then start the domain
        stop           poolrm, if enabled, stop the domain
        ...
    Types:
        app            act on application domains
        prcs           act on process scheduler domains
        web            act on web domains
        all,<blank>    act on all types of domains
    Domains:
        dom            act on specific domains
        all,<blank>    act on all domains
```

---

# psa examples

* `psa help`           - help menu
* `psa start`          - start all domains on server
* `psa start web`      - start all web domains on server
* `psa start web hdev` - start hdev web domain on server
* `psa bounce`         - stop, cache, IPC, configure, start all domains

---

# psa install

* Install Ruby, RubyGems...or use Puppet's

*Linux*
```bash
export PATH=$PATH:/opt/puppetlabs/puppet/bin
gem install psadmin_plus
psa
```

*Windows*
```powershell
$env:PATH += ";C:\Program Files\Puppet Labs\Puppet\sys\ruby\bin"
gem install psadmin_plus
psa
```

> NOTE: For Windows, you will need to [update the RubyGemsRootCA certificate](https://gist.github.com/iversond/772e73257c4ca59a9e6137baa7288788); the DPK ships an outdated version.

---

class: center, middle, black

# Demo

???

```bash
sudo /opt/puppetlabs/puppet/bin/gem install psadmin_plus
export PATH=$PATH:/opt/puppetlabs/puppet/bin

psa
psa list
psa status app
# hidden psadmin option
psa summary

# hooks for LB pool members (modify a healthcheck file)
export PS_HEALTH_TIME=5
psa list
# show config values for Time and File
psa poolrm
psa restart web
# pooladd is included in restart action

psa stop app psftdb
psa configure app psftdb
psa start app psftdb

# combine domain types
psa bounce app,prcs psftdb



tail -f /opt/oracle/psft/cfg/webserv/psftdb/servers/PIA/logs/PIA_* | grep RUNNING
```