class: center, middle, blue

# ACM and Elasticsearch

---

# Elasticsearch and ACM

* Automated Configuration Management
--

* Database Configuration
--

* Leverages SQL **and** PeopleCode
--

* Search Framework Plugins
--

* Configure **and** Deploy Search Indexes

---

class: center, middle, white

# Demo

![Demo](../images/esacm.jpg)

???
Tasks:

1. Configure ES Cluster
1. Clear previous ES Deployment Data
1. Redeploy ALL indexes

*ACM and Search Framework Demo*

1. Use the `SEARCH_TEMPLATE` ACM plugin
1. Configure a 3 node cluster (pre-configured)
1. Remove previously deployed PTSF data

    This removes it from the PSTF* tables, but not Elasticsearch

1. Deploy ALL indexes and start a full build for each
1. Show the run controls for the builds (full and incr)