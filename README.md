# Ansible Ssmtp Role

[![Build Status](https://img.shields.io/travis/weareinteractive/ansible-ssmtp.svg)](https://travis-ci.org/weareinteractive/ansible-ssmtp)
[![Galaxy](http://img.shields.io/badge/galaxy-franklinkim.ssmtp-blue.svg)](https://galaxy.ansible.com/list#/roles/)
[![GitHub Tags](https://img.shields.io/github/tag/weareinteractive/ansible-ssmtp.svg)](https://github.com/weareinteractive/ansible-ssmtp)
[![GitHub Stars](https://img.shields.io/github/stars/weareinteractive/ansible-ssmtp.svg)](https://github.com/weareinteractive/ansible-ssmtp)

> `ssmtp` is an [ansible](http://www.ansible.com) role which:
>
> * installs ssmtp
> * configures ssmtp
> * manages
> * configures service

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.ssmtp
```

Using `requirements.yml`:

```
- src: franklinkim.ssmtp
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-ssmtp.git franklinkim.ssmtp
```

## Dependencies

* Ansible >= 1.9

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
- hosts: all
  sudo: yes
  roles:
    - franklinkim.ssmtp
  vars:
    ssmtp_root: admin@example.com
    ssmtp_mailhub: smtp.mandrillapp.com:587
    ssmtp_auth_user: the_mandrill_account_username
    ssmtp_auth_pass: the_mandrill_api_key
```

## Handlers

These are the handlers that are defined in `handlers/main.yml`.

* `restart ssmtp`

## Example playbook

```
- hosts: all
  sudo: yes
  roles:
    - franklinkim.ssmtp
  vars:
    ssmtp_service_enabled: yes
    ssmtp_service_state: started
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-ssmtp.git
$ cd ansible-ssmtp
$ vagrant up
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License
Copyright (c) We Are Interactive under the MIT license.
