Original work https://git.elukerio.org/mablr/ansible-role-rss-bridge

```
---
- hosts: all
  become: true
  tasks:
    - name: Install gpg
      apt: name="{{item}}" update_cache=yes state=present
      loop:
        - git
        - gpg
        - gpg-agent
- hosts: all
  become: true
  vars:
    rssb_bridges:
      - Telegram
      - Twitter
  roles:
    - ansible-role-rss-bridge
```
