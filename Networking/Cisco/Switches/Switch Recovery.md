to enter a Cisco switch recovery system is different froma  routers recovery system called rommon so on the switch hold the mode button at the front of the switch while booting you want to be sure you are consoled into the device using these configs [[Consoling]] you will boot into a system with a switch: option now you want to run these commands. ```
flash_init

```arduino
del flash:config.text
```


```css
del flash:vlan.dat
```




```
boot
```


now you really want to pay attention as the device boots and look for a option called baud rate, this is important as some people like to chnage this and it makes it a real pain to accses the switch as it boots and you will see random symbols. so look for something like setting console baud rate to 57600 now look back at the [[Consoling]] settings and change the baudrate from