# ipfw-spamhaus-drop
Fetch and add DROP list from Spamhaus

This shell script fetches DROP lists from Spamhaus and loads ipfw tables.

## How to install
Regularly download this repository. Then,

1. Move the script into your periodic folder
```
sudo mv 600.spamhaus-drop /etc/periodic/daily
```

2. Change permissions
```
sudo chown root:wheel /etc/periodic/daily/600.spamhaus-drop
sudo chmod 755 /etc/periodic/daily/600.spamhaus-drop
```

3. Amend the new rules to your ipfw firewall:
```
ipfw add 00550 deny ip from "table(2)" to me
ipfw add 00551 deny ip from "table(3)" to me
ipfw add 00552 deny ip from "table(4)" to me
```
