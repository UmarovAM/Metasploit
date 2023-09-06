## Домашнее задание к занятию «Уязвимости и атаки на информационные системы» Умаров Азиз
# Задание 1
## Разрешенные сетевые службы
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/002e4fea-b7bb-4dca-ad34-de2f12fdf246)

## Обнаружены Уязвимости
### 1. auxiliary/admin/smb/samba_symlink_traversal
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/52d65032-c938-459f-a4bb-aa41d585611b)

### 2. exploit(unix/ftp/vsftpd_234_backdoor)
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/fd9844d4-c601-4c2c-a162-aa30fd36359a)

### 3. use exploit/multi/misc/java_rmi_server
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/51140842-260d-49e0-8caa-54b55164097a)

# Задание 2

## Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.
## Запишите сеансы сканирования в Wireshark.

### Cканирование Metasploitable в режимах SYN.
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/466ec4ce-607c-4d9e-88fe-2e7b20601834)
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/c95161e2-4aab-428c-9f1f-a1bcbe876425)

### Cканирование Metasploitable в режимах FIN.
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/7060ecf4-1e14-4e27-a3a9-bd4170290d20)
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/30b3a941-c25e-4803-a721-b0c1f4bf2af3)

### Cканирование Metasploitable в режимах Xmas.
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/3b6a45b0-7ef6-4b02-8e80-dc04c832dc7b)
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/1ca80e67-1ff9-4628-a7d9-6ad654e85ab9)

### Cканирование Metasploitable в режимах UDP.
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/1e105e20-51e6-41f8-b021-31c58d2de2ac)
![image](https://github.com/UmarovAM/Metasploit/assets/118117183/3abcdb34-cb2e-451f-9d90-fb4bdca0e8ae)

## Ответьте на следующие вопросы:
### Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?

Cканирование Metasploitable в режимах SYN, FIN, Xmas использует TCP протокол на запрос и ответ, если получена ошибка недоступности ICMP порт также помечается как отфильтрованный.

Сканирование Metasploitable в режиме UDP отправка происходит через протокол UDP, если получена ошибка недоступности ICMP порт также помечается как отфильтрованный или закрыт 

### Как отвечает сервер?

Сканирование SYN “Half-open” (-sS)
После получения пакета SYN/ACK мы отправляем RST-пакет. Это предотвращает повторные попытки сервера выполнить запросы и значительно сокращает время сканирования.

Сканирование TCP FIN (-sF)
Отправляет пакет с установленным флагом FIN, который используется для корректного закрытия соединения. Цель должна ответить RST для closed портов, в соответствии с RFC.

3: Сканирование TCP Xmas (-sX)
ИспользуетTCP-пакеты с установленными флагами PSH, URG и FIN. Как и в предыдущих двух типах сканирования, этот тип также ожидает пакеты RST для closed портов в соответствии с RFC.

