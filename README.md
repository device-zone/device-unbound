# device-unbound
Provides an Unbound appliance.

The appliance provides a default installation of the unbound DNS service, which
is in turn enabled through the use of device-unbound-resolver.


# device-unbound-resolver
Provides an Unbound appliance so the localhost can resolve DNSSEC securely.

This appliance does the following:

- All parameters passed to the device commands are syntax checked and canonicalised, with bash completion.
- Installs a local unbound caching nameserver, available on ::1.
- Updates /etc/resolv.conf to use local unbound for DNS queries.
- Enables ability to securely handle DNSSEC without having to trust the network.
- Autostarts on server restart.
- Zero Trust configuration.

## before

- Deploy the device-unbound-resolver package.

```
[root@server ~]# dnf install device-unbound-resolver
```

## enable

To switch the appliance on, run this.

```
[root@server ~]# device services dns resolver enable 
```

## disable

To switch the appliance off, run this.

```
[root@server ~]# device services dns resolver disable  
```



