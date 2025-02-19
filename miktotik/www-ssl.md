## Some useful Links
- https://mikrotik.com/download
- https://help.mikrotik.com/docs/spaces/ROS/pages/2555969/Certificates
- https://help.mikrotik.com/docs/spaces/ROS/pages/47579229/Scripting
- https://help.mikrotik.com/docs/spaces/ROS/pages/328131/WebFig
- https://www.medo64.com/2016/11/enabling-https-on-mikrotik/

### Get IP-address from system (search multiple interfaces) into variable
```routeros
:global thisIP [/ip address get [find interface="bridgeLocal","vl_mgmt"] address]
:global thisIP [:pick $thisIP 0 [:find $thisIP "/"]]
```

### Get system ididentitiy into variable
```routeros
:global thisBox [/system identity get name]
```

### alternative names for creating certificates
```routeros
subject-alt-name=DNS:a.com,DNS:b.com,DNS:c.com
```

### Create root-cert :
```routeros
certificate add name=local-cert common-name=local-cert days-valid=3650 key-usage=key-cert-sign,crl-sign
certificate sign local-cert
```
### Create certificate for WebFig
```routeros
:global thisBox [/system identity get name]
:global thisIP [/ip address get [find interface="bridgeLocal","vl_mgmt"] address]
:global thisIP [:pick $thisIP 0 [:find $thisIP "/"]]
certificate add name=webfig common-name=$thisIP subject-alt-name="DNS:$thisBox,DNS:$thisBox.local" days-valid=3650
certificate sign webfig 
certificate print
```
### Enalbe www-ssl and disable www
```routeros
ip service set www-ssl certificate=webfig disabled=no
ip service set www disabled=yes
```


