## dir

```
.
|-- conf.d
|   `-- sample.conf
|-- config
|-- keys
|   `-- sample.key
`-- known_hosts
```

### config file
```
Include ~/.ssh/conf.d/**/*.conf

Host *
  Host ServerAliveInterval 300
```

### conf.d

```
Host s1
  HostName 192.168.56.10
  User user_name
  Port 22
  IdentityFile ~/.ssh/keys/sample_s1.key

Host _s2
  HostName 192.168.100.110
  User user_name
  Port 1234
  IdentityFile ~/.ssh/keys/sample_s2.key

// if you need proxy server...
Host _*
  ProxyCommand ssh -W %h:%p s1
```
