<h> Hurtig set up af fortigat gui <h/>

```
config system interface
  edit "port1"
    set ip 192.168.10.99 255.255.255.0
    set allowaccess ping https ssh
    set alias "LAN"
  next 
end
config system dhcp server
    edit 1
        set dns-service default
        set default-gateway 192.168.10.99
        set netmask 255.255.255.0
        set interface "port1"
        config ip-range
            edit 1
                set start-ip 192.168.10.2
                set end-ip 192.168.10.254
            next
        end
    next
end

```


