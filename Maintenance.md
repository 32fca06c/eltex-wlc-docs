# Обслуживание контроллера
## Создание виртуальной машины  
```
qemu-system-x86_64 \
  -name "test" \
  -machine type=pc-i440fx-9.1,accel=kvm \
  -m 3G \
  -smp 1 \
  -cpu kvm64 \
  -drive file=%image_path%,if=ide,media=disk,format=qcow2,size=8G \
  -cdrom %iso_path% \
  -netdev user,id=net0 \
  -device e1000,netdev=net0 \
  -vnc :0 \
```
`%iso_path%` -   
`%image_path%` -   

## Включение виртуального консольного порта  
```
syslog console
 virtual-serial
exit
```

## Метаданные файла конфигурации  
```shell
#!/usr/bin/clish
#%code%
#%version%
```

`%code%` - версия схемы конфигурации  
`%version%` - версия ПО  

| Code | Version |
| ---- | ------- |
|      | 1.30.8  |
| 303  | 1.30.6  |
|      | 1.30.4  |
| 300  | 1.30.2  |
| 270  | 1.30.0  |
|      | 1.26.1  |
|      | 1.19.2  |
|      | 1.19.1  |
|      | 1.19.0  |
|      | 1.15.3  |

## Обновление ПО точек доступа
```
copy https://api.prod.eltex-co.ru:/storage/upload_center/files/50/WEP-30L-2.8.2_build_36.tar.gz system:access-points-firmwares
```


```
show storage-devices usb
dir usb://FIRMWARE:/
```

```
copy usb://FIRMWARE:/WEP-2ac-1.25.4.9.tar.gz system:access-points-firmwares
```

## Обновление ПО контроллера
```
copy https://api.prod.eltex-co.ru:/storage/upload_center/files/55/wlc30-1.30.8-build3.firmware system:firmware
```
```
copy usb://FIRMWARE:/wlc30-1.30.8-build3.firmware system:firmware
```
```
boot system inactive
reload system
```
