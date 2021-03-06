---
id: page-install-method
title: Install - Ubuntu
header_title: Ubuntu Installation
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---

### Packages:

Start by downloading the corresponding package for your configuration:

- [12.04 Precise]({{ site.links.download }}/{{site.data.kong_latest.version}}/kong-{{site.data.kong_latest.version}}.precise_all.deb)
- [14.04 Trusty]({{ site.links.download }}/{{site.data.kong_latest.version}}/kong-{{site.data.kong_latest.version}}.trusty_all.deb)
- [15.04 Vivid]({{ site.links.download }}/{{site.data.kong_latest.version}}/kong-{{site.data.kong_latest.version}}.vivid_all.deb)
- [16.04 Xenial]({{ site.links.download }}/{{site.data.kong_latest.version}}/kong-{{site.data.kong_latest.version}}.xenial_all.deb)

### APT Repositories

You can also install Kong by using the following APT repositories and following the Bintray instructions:

- [12.04 Precise APT](https://bintray.com/mashape/kong-ubuntu-precise-{{site.data.kong_latest.release}})
- [14.04 Trusty APT](https://bintray.com/mashape/kong-ubuntu-trusty-{{site.data.kong_latest.release}})
- [15.04 Vivid APT](https://bintray.com/mashape/kong-ubuntu-vivid-{{site.data.kong_latest.release}})
- [16.04 Xenial APT](https://bintray.com/mashape/kong-ubuntu-xenial-{{site.data.kong_latest.release}})

----

### Installation:

1. **Install the Package:**

    If you are downloading the [package](#packages), execute:

    ```bash
    $ sudo apt-get update
    $ sudo apt-get install netcat openssl libpcre3 dnsmasq procps perl
    $ sudo dpkg -i kong-{{site.data.kong_latest.version}}.*.deb
    ```

2. **Configure your database**

    [Configure][configuration] Kong so it can connect to your database. Kong supports both [PostgreSQL {{site.data.kong_latest.dependencies.postgres}}](http://www.postgresql.org/) and [Cassandra {{site.data.kong_latest.dependencies.cassandra}}](http://cassandra.apache.org/) as its datastore.

    If you are using Postgres, please provision a database and a user before starting Kong, ie:

    ```sql
    CREATE USER kong; CREATE DATABASE kong OWNER kong;
    ```

3. **Start Kong:**

    ```bash
    $ kong start

    # Kong is running
    $ curl 127.0.0.1:8001
    ```

4. **Use Kong:**

    Quickly learn how to use Kong with the [5-minute Quickstart](/docs/latest/getting-started/quickstart).

[configuration]: /docs/{{site.data.kong_latest.release}}/configuration#database
