Ansible-плейбук для сканирования запрошенных серверов при помощи nmap
===
В репозитории предоставлен файл с YAML разметкой, ini-файл с ip исполняющей машины, txt со сканируемыми серверами и скрин с результатом 

### Порядок выполнения работы
- Обновляю модуль apt
> sudo apt update
- устанавливаю nmap
> sudo apt install nmap
- создаю папку
> mkdir ansible_nmap_folder
- создаю ini-файл и пишу туда ip своей машины, с которой буду делать сканирование
> touch inventory.ini
> cat >> inventory.ini
> [nmap servers]
> 192.168.56.102
- создаю плейбук
> touch pb_nmap.yml
- пишу разметку
- создаю текстовик со сканируемыми серверами
> touch targets.txt
> cat >> targets.txt
> etis.psu.ru
> psu.ru
> yandex.ru
- копирую ключи в систему(потому что у меня происходит подключение по ключу)
> ssh-copy-id vboxuser192.168.56.102
- Теперь выполняю плейбук(inventory.ini - исполняющие машины, -diff - вывод изменений, --ask-become-pass - запрос пароля)
> ansible-playbook pb_nmap.yml -i inventory.ini --diff --ask-become-pass
- Получаем результат сканирования
