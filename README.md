# What is this?

An Ansible playbook for installing Magento 2 on CentOS 6.x.

It also installs the Japanese language pack and the Omise module since I need it. If you don't need them, see the installation section.

# Prerequisites

* Ansible 2.2 or above (maybe 2.0 and 2.1 also work)

```
ansible-galaxy install geerlingguy.composer
```

# How to use it?

All the file paths are relative to `centos6` directory.

* Edit the following files:
    * `prod_hosts`
    * `group_vars/webservers`
    * `stage_vars/production.yml`
* Obtain the following files and place them under `roles/webtier/files/magento2` if you need them:
    * `veriteworks-m2-japaneselocale-1.1.0.zip`
    * `omise-magento-master.zip`

## Customize

If you don't need the Japanese language pack or the Omise module, please comment out the lines for them in `roles/webtier/tasks/*`.

If you tweak the installation options, please see the following page for more details:
http://devdocs.magento.com/guides/v2.1/install-gde/install/cli/install-cli-install.html

# Notes

I uploaded this project mainly for myself, so I don't provide any support. Though, PRs would be welcome.

I chose CentOS 6.x because 7.x seems to have an issue with libicu when using Magento 2 in Japanese (and some other Asian lauguages). See the following pages for the details:

* https://github.com/magento/magento2/issues/5356
* http://qiita.com/kzkiq2nd/items/48eb7f559f3342b74195 (Japanese)

Switching to CentOS 7 shouldn't be difficult.

# License

[Apache License, Version 2](http://www.apache.org/licenses/LICENSE-2.0.html)
