# Ansible Scripts for Hosting Modded Minecraft Servers in AWS

## Quickstart

To start, step by step 

1. Create a r8g.* persistant spot instance in AWS with Amazon Linux AMI.
2. Allow access from TCP port 21 and 25566 on your computers IP
3. Allow access from TCP port 25565 on computers which are going to connect to server.
4. Save your ssh public key to a known secure location
5. Note your instances public ip (you might want an elastic ip for consistency).
6. Create an inventory file as:

```
[ec2:vars]
ansible_ssh_private_key_file=<PATH TO SSH KEY>

[ec2]
<INSTANCE PUBLIC IP> ansible_user=ec2-user
```

7. Use `ansible-playbook --become --inventory inventory <modpack>.yaml` to setup your server.
8. Connect your server with its public ip, you can also use rcon to administer your server.

## Which version of modpacks are supported ?

| **Modpack** | **Version** |   **Forge**   |
|:-----------:|:-----------:|:-------------:|
|    ATM 9    |    0.3.0    |               |
| Monifactory |    0.7.7    | 1.20.1-47.3.0 |
