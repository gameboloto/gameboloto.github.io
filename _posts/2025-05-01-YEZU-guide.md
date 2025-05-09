---
title: Как поиграть по онлайну через эмулятор Yuzu
description: >-
  Небольшой гайд по настройке эмулятора yuzu 2025.
date: 2025-03-09 12:03:01 +0300
categories: [Видеоигры, Гайды]
tags: [nintendo, yuzu, эмуляторы]     # TAG names should always be lowercase
---
![title](images/yezu_mario.jpeg)

1 Нам нужен жмулятор Yuzu Early access 4176 (желтый) -
https://web.archive.org/web/20240304183636if_/https://objects.githubusercontent.com/github-production-release-asset-2e65be/325036684/07a276e4-e6c6-4fac-b5ec-15aa3224ec4e?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20240304%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20240304T183634Z&X-Amz-Expires=300&X-Amz-Signature=e25139db5d6c11c43852233455fe51a2c25e52a267674421b54d07fd5d5eb8b2&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=325036684&response-content-disposition=attachment%3B%20filename%3DWindows-Yuzu-EA-4176.zip&response-content-type=application%2Foctet-stream

2 нужны файлы ключей и прошивки 17.0 или 17.0.1

тема на 4пда - https://4pda.to/forum/index.php?showtopic=1070467&st=4420
ссылка пост на 4пда - https://4pda.to/forum/index.php?act=findpost&pid=126024483&anchor=Spoil-126024483-1
Если не качает регайтесь на 4пда. 

2.1 Прошивка 17.0.1 - https://4pda.to/stat/go?u=https%3A%2F%2Fgithub.com%2FTHZoria%2FNX_Firmware%2Freleases%2Fdownload%2F17.0.1%2FFirmware.17.0.1.zip&e=126024483
2.1 Прошивка 17.0 -  https://4pda.to/stat/go?u=https%3A%2F%2Fgithub.com%2FTHZoria%2FNX_Firmware%2Freleases%2Fdownload%2F17.0.0%2FFirmware.17.0.0.zip&e=126024483

2.2 Ключ 17.0.1 - https://4pda.to/forum/dl/post/30268747/Keys%2B17.0.1.7z
2.2 Ключ 17.0 - https://4pda.to/forum/dl/post/29483267/Prod%2BKeys%2B17.0.0.zip


3 Yuzu использует только игры формата NZS, то там нужен конвертер скачанных игр NSZ в NSP -
https://4pda.to/forum/dl/post/32495158/nsz_v4.6.1_win64_portable.rar
https://github.com/nicoboss/nsz

https://4pda.to/forum/index.php?showtopic=1070467&view=findpost&p=135125762


3.1 Нужно создать папку свитч по адресу %USERPROFILE%/.switch/     (C:\Users\вашеимяпользователявиндовс\.switch) и туда копируем копию ключа, который скачали выше 2.2 
3.2 уставливаем питон https://www.python.org/downloads/

4 Конвертируем игры. Заходим в папку NZS. На вин11 ПКМ - Открыть в терминале. 
На вин<10 открываем терминал через пуск пишем - CD D: если папка с NZD на диске Д. Если на Ц, то сразу пишем CD "путь до папки NZD". Например 
CD E:\nsz_v4.6.1_win64_portable

Далее пишем в консоль pip3 install --upgrade nsz[gui]
Должен установиться GUI

5 Запускаем NSZ.py в Select Input выбираем скачанную игру в select output выбираем папку куда будут сохраняться сконвертированные образы.
Выбираем все файлы из списка, чтобы они были зеленые. 
Далее выбираем Decompress NSZ 

6 В Yuzu выбираем File - Open config. ЗАКРЫВАЕМ YEZU ОБЯЗАТЕЛЬНО ПОСЛЕ ЭТОГО.
В папке ищем config папку, далее qt-config открываем блокнотом.

6.1 Ищем строчку [WebService] и меняем ниже чтобы было вот так - 

[WebService]
enable_telemetry\default=false
enable_telemetry=false
web_api_url\default=false
web_api_url=api.ynet-fun.xyz

Сохраняем. Делаем это обязательно при ВЫКЛЮЧЕННОМ YEZU (закрыть программу)

В меню YUZU - Muiltiplayer должны появиться комнаты. 

7 В YEZU добавляем папку с нашими конвертированными играми. Должна появиться обложка игры.

8 Как установить патч на игру? 
Заходим в верхнее меню YEZU - Files - Install files to NAND. Выбираем патч.

9 В YUZU - EMULATION - CONFIG - SYSTEM - NETWORK - выбираем вместо NONE - Internet

10 В меню YUZU - Muiltiplayer заходим в комнату - в игре заходим в ЛАН или мультиплеер.

В Марио карт 8 чтобы включить ЛАН в главном меню жми Л+Б + левый стик. Вместо Wireless play появится LAN 
Возможно вам потребуется открыть порты на роутере 5000 и 4000 порты tcp/udp оба


Ссылка на гайд Yuzu в дискорде yuzu online https://discord.com/channels/1084911987626094654/1292712644884697141