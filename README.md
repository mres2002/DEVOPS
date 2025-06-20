Ansible-плейбук
===
В репозитории предоставлен файл с YAML разметкой и HTML-файл, выводимый на странице сайта:

### Порядок выполнения работы
- В сетевых настройках ставлю два адаптера - 1:виртуальный адаптер хоста, 2:NAT
- генерирую и вставляю ключ
> ssh-keygen -t rsa
> cat .ssh/id_rsa > ./ssh/authorized_keys
- скачиваю сам ансибл
> sudo apt install ansible
- создаю директорию и файл для .yml и .html
> mkdir pb_folder
> touch playbook.yml
> touch index.html
- пишу разметку .yml
- пишу разметку .html
- настраиваю правила проброса портов
- исполняю yaml скрипт
> sudo ansible-playbook playbook.yml
