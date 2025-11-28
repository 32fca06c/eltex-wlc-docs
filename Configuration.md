```
wlc
  outside-address 192.168.1.40
  service-activator
    aps join auto
  exit
  airtune
    enable
  exit
  failover
  ap-location default
    mode tunnel
    ap-profile default
  exit
  radio-2g-profile default_2g
    work-mode nax
    tx-power minimal
    rates-supported 12,18,24,36,48,54
    rates-basic 12,24
  exit
  radio-5g-profile default_5g
    tx-power minimal
    limit-channels 36,40,44,48,52,56,60,64,132,136,140,144,149,153,157,161,165
    rates-supported 12,18,24,36,48,54
    rates-basic 12,24
  exit
  ap-profile default
    password ascii-text encrypted 8CB5107EA7005AFF
  exit
  ip-pool default
    ap-location default
    network 0.0.0.0/0
  exit
  update-manager
    scheduled
    start-time 00:00
    end-time 06:00
  exit
  enable
exit
```
