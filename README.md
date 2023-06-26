# Title: ssh_script.sh
Author: G0TH3R


```bash
#!/bin/bash

# Script to SSH into a remote server using sshpass and specific SSH options

# Check if all required arguments are provided
if [ $# -ne 3 ]; then
    echo "Usage: $0 <remote_user> <remote_password> <remote_host>"
    exit 1
fi

# Assign command-line arguments to variables
remote_user="$1"
remote_password="$2"
remote_host="$3"


# SSH command with sshpass and SSH options
sshpass -p "$remote_password" ssh \
-o "UserKnownHostsFile=/dev/null" \
-o "StrictHostKeyChecking=no" \
"$remote_user@$remote_host"


# Make into an alias
# alias ssh-rem='/path/to/ssh_script.sh'
# source ~/.bashrc
# ssh-rem username password 192.168.1.251
```



## Copyright 2021 G0TH3R

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
