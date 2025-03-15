## Issues faced when trying to use the ssh-copy-id command

#OlatunbosunsMBP:Downloads bosman$ ssh-copy-id -f "-o IdentityFile ~/Downloads/tester.pem" ubuntu@44.204.232.140
#/usr/bin/ssh-copy-id: ERROR: No identities found

## Solution can be found here : 
https://labex.io/tutorials/linux-how-to-resolve-ssh-copy-id-no-identities-found-error-398384

# How to setup Passwordless Authentication

## EC2 Instances

### Using Public Key

```
ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
```

- ssh-copy-id: This is the command used to copy your public key to a remote machine.
- -f: This flag forces the copying of keys, which can be useful if you have keys already set up and want to overwrite them.
- "-o IdentityFile <PATH TO PEM FILE>": This option specifies the identity file (private key) to use for the connection. The -o flag passes this option to the underlying ssh command.
- ubuntu@<INSTANCE-IP>: This is the username (ubuntu) and the IP address of the remote server you want to access.

### Using Password 

- Go to the file `/etc/ssh/sshd_config.d/60-cloudimg-settings.conf`
- Update `PasswordAuthentication yes`
- Restart SSH -> `sudo systemctl restart ssh`
