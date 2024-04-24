boot into the existing image and run these commands 



```bash
enable
```

```
configure terminal
```

```kotlin
interface vlan 1
```

```php-template
ip address <IP_ADDRESS> <SUBNET_MASK>
```

`no shutdown`


exit


```kotlin
show ip interface brief
```

```kotlin
interface GigabitEthernet0/1
no shutdown
```

```kotlin
show interface GigabitEthernet0/1
```


```lua
show interfaces status
```

```go
copy tftp: flash:
```


```sql
copy flash:ios-image.bin system:
```


```arduino
config terminal
boot system flash:ios-image.bin
end
```
```arduino
write memory
```



