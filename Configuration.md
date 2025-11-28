
```shell
wlc
  ap-profile default-ap
    description "default-ap"
    password ascii-text encrypted 8CB5107EA7005AFF
  exit
exit
```

```shell
wlc
  airtune-profile default_airtune
    description "default_airtune"
  exit
exit
```

```shell
wlc
  radius-profile default-radius
    description "proxy"
    auth-address %ip_wlc%
    auth-password ascii-text encrypted 8CB5107EA7005AFF
    domain default
  exit
exit
```

```shell
wlc
  ssid-profile default-ssid
    description "default-ssid"
    ssid "default-ssid"
    radius-profile default-radius
    vlan-id %vlan_id%
    security-mode WPA2_1X
    802.11kv
    band 2g
    band 5g
    enable
  exit
exit
```

```shell
wlc
  ap-location default-location
    description "default-location"
    mode tunnel
    ap-profile default-ap
    airtune-profile default_airtune
    ssid-profile default-ssid
  exit
exit
```

```shell
wlc
  ip-pool default-ip-pool
    description "default-ip-pool"
    ap-location default-location
  exit
exit
```

```shell
wlc
  radio-2g-profile default_2g
    description "default_2g"
    work-mode nax
    tx-power minimal
    rates-supported 12,18,24,36,48,54
    rates-basic 12,24
  exit
  radio-5g-profile default_5g
    description "default_5g"
    work-mode anacax
    dfs auto
    tx-power low
    limit-channels 36,40,44,48,52,56,60,64,132,136,140,144,149,153,157,161,165
    rates-supported 12,18,24,36,48,54
    rates-basic 12,24
  exit
exit
```

```shell
wlc
  airtune
   enable
  exit
exit
```

```shell
wlc
  outside-address %ip_wlc%
exit
```

```shell
wlc
 service-activator
   aps join auto
 exit
exit
```

```shell
wlc
  enable
exit
```
