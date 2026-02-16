Финальный рывок — установка samba-common-bin
1. Скачай пакет (ссылка рабочая)
bash
cd ~/ad-setup
wget http://archive.debian.org/debian/pool/main/s/samba/samba-common-bin_4.9.5+dfsg-5+deb10u3_amd64.deb
2. Установи
bash
sudo dpkg -i samba-common-bin_4.9.5+dfsg-5+deb10u3_amd64.deb
3. Если будут ошибки зависимостей
bash
sudo apt install -f
После установки — регистрируем компьютер в домене
Вариант А — через скрипт
bash
sudo ~/join-ad.sh Администратор
Скрипт теперь найдёт команду net и завершит регистрацию.

Вариант Б — вручную
bash
sudo net ads join -k
Использует уже полученный билет.

Проверка после регистрации
bash
realm list
Должен появиться твой домен.

И наконец — перезагрузка
bash
sudo reboot
После перезагрузки вход под доменной учёткой должен работать.
