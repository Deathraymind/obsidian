- boot into the existing image and run these commands #switch #cisco 
  
  
  
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
  boot system flash:c2960-lanbasek9-mz.150-2.SE11.bin
  ```
  ```
  
  
  ```arduino
  config terminal
  boot system flash:ios-image.bin
  end
  ```
  ```arduino
  write memory
  ```