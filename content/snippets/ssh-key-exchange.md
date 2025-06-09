---
title: "SSH Key Exchange"
draft: true
---

![alt](//via.placeholder.com/640x150)

When you need to setup ssh using keys, I use `ssh-copy-id`.

The help for the command is:

```
Usage: /usr/bin/ssh-copy-id [-h|-?|-f|-n|-s|-x] [-i [identity_file]] [-t target_path] [-F ssh_config] [[-o ssh_option] ...] [-p port] [user@]hostname
        -f: force mode -- copy keys without trying to check if they are already installed
        -n: dry run    -- no keys are actually copied
        -s: use sftp   -- use sftp instead of executing remote-commands. Can be useful if the remote only allows sftp
        -x: debug      -- enables -x in this shell, for debugging
        -h|-?: print this help
```

The simplest usage is 

```ssh-copy-id user@hostname```

__Note__: requires the account already exist and the hostname is reachable via ssh.