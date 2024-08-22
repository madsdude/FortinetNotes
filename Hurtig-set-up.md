<h> Hurtig set up af fortigat gui <h/>

```
config system interface
  edit "port1"
    set ip 192.168.10.99 255.255.255.0
    set allowaccess ping https ssh
    set alias "LAN"
  next 
end

```


