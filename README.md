# Linux_Lesson_27
## Network architecture
Сетевая лаборатория из устройств на основе GNU Linux  

![lan](https://github.com/darknetworm/Linux_Lesson_27/assets/82410807/dd0adc24-7bf1-4f29-8ffd-8733e258483c)

### Теоретическая часть
Для расчетов используется утилита ipcalc
| Подразделение | Имя сети | ip-адрес сети | Маска сети | Количество хостов | Минимальный ip-адрес | Широковещательный адрес |
| --- | --- | --- | --- | --- | --- | --- |
| Internet | Inet | 192.168.255.0 | 255.255.255.252 | 2 | 192.168.255.1 | 192.168.255.3 |
| Central | Directors | 192.168.0.0 | 255.255.255.240 | 14 | 192.168.0.1 | 192.168.0.15 |
| *Central* | *FREE* | *192.168.0.16* | *255.255.255.240* | *14* | *192.168.0.17* | *192.168.0.31* |
| Central | Office hardware 1 | 192.168.0.32 | 255.255.255.240 | 14 | 192.168.0.33 | 192.168.0.47 |
| *Central* | *FREE* | *192.168.0.48* | *255.255.255.240* | *14* | *192.168.0.49* | *192.168.0.63* |
| Central | Office hardware 2 | 192.168.0.64 | 255.255.255.192 | 62 | 192.168.0.65 | 192.168.0.127 |
| *Central* | *FREE* | *192.168.0.128* | *255.255.255.128* | *126* | *192.168.0.129* | *192.168.0.255* |
| Office 1 | Dev | 192.168.2.0 | 255.255.255.192 | 62 | 192.168.2.1 | 192.168.2.63 |
| Office 1 | Test Servers | 192.168.2.64 | 255.255.255.240 | 14 | 192.168.2.65 | 192.168.2.79 |
| *Office 1* | *FREE* | *192.168.2.80* | *255.255.255.240* | *14* | *192.168.2.81* | *192.168.2.95* |
| *Office 1* | *FREE* | *192.168.2.96* | *255.255.255.224* | *30* | *192.168.2.97* | *192.168.2.127* |
| Office 1 | Managers | 192.168.2.128 | 255.255.255.192 | 62 | 192.168.2.129 | 192.168.2.191 |
| Office 1 | Office hardware | 192.168.2.192 | 255.255.255.192 | 62 | 192.168.2.193 | 192.168.2.255 |
| Office 2 | Dev | 192.168.1.0 | 255.255.255.128 | 126 | 192.168.1.1 | 192.168.1.127 |
| Office 2 | Test Servers | 192.168.1.128 | 255.255.255.192 | 62 | 192.168.1.129 | 192.168.1.191 |
| Office 2 | Office hardware | 192.168.1.192 | 255.255.255.192 | 62 | 192.168.1.193 | 192.168.1.255 |

Таким образом в подразделении **Central** имеется 3 свободных подсети, в подразделении **Office 1** - 2 свободных подсети.  
> [!WARNING]
> В подразделении **Office 1** для сети **Office hardware** минимально допустимым ip-адресом является 192.168.2.193, в то время как на office1Router интерфейсу назначен недопустимый ip-адрес 192.168.1.192.

---

### Описание репозитория
