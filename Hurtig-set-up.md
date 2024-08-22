<h> Hurtig set up af fortigat gui <h/>

```
config system interface
  edit "port1"
    set ip 192.168.10.99 255.255.255.0
    set allowaccess ping https ssh
    set alias "LAN"
  next 
end

config router static

edit 1

set gateway 172.31.1.1

set device port1

end

config system dns

set primary 208.91.112.53

set secondary 208.91.112.52

end


```


