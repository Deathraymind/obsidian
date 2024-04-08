Its simple to pin cpus to be used for the OS just add this too the XML file for the VM
```
 <currentMemory unit="KiB">16580608</currentMemory>
  <vcpu placement="static">8</vcpu>
  <iothreads>1</iothreads>
  <cputune>
    <vcpupin vcpu="0" cpuset="1"/>
    <vcpupin vcpu="1" cpuset="2"/>
    <vcpupin vcpu="2" cpuset="3"/>
    <vcpupin vcpu="3" cpuset="4"/>
    <vcpupin vcpu="4" cpuset="5"/>
    <vcpupin vcpu="5" cpuset="6"/>
    <vcpupin vcpu="6" cpuset="7"/>
    <vcpupin vcpu="7" cpuset="8"/>
    <emulatorpin cpuset="0,8"/>
    <iothreadpin iothread="1" cpuset="0,8"/>
  </cputune>
```
 <vcpupin vcpu="0" cpuset="1"/>

vcpu is the virtual CPU core aka what shows in windows.
cpuset is the physical thread add and remove what you want.
