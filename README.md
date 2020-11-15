# vagrant-ansible-jenkins-CI

Этот проект представляет собой решение задачи по автоматизации и создания CD/CI

Системные требования:

Должны быть установлены:

virtualbox
vagrant
ansible


Запуск:

После клонирования проекта в папку, необходимо зайти в нее в терминале и ввести команду

vagrant up

После этого vagrant  создаст с помощью virtualbox  две виртуальные машины с операционными системами
centos7 и ubuntu, и запустит для каждой из них плейбук Ansible.

С помощью Ansible на них будут установлены:

Java
Git
Maven
Jenkins

Jenkins будет установлен с помощью роли geerlingguy.jenkins, скачанной с сайта ansible-galaxy

поскольку установка плагинов jenkins  не работает в этой роли, они будут установлены с помощью моих 
плейбуков.


В Jenkins будут установлены плагины:
greenballs
chucknorris
Warnings Next Generation
Plugin Git

Затем будет установлен job  с  помощью JCI.

плейбук периодически скачивает с репозитория гитхаба мавен проект, собирает его с помощью мавена, генерирует артефакт 
с jAR  файлом.
Кроме того формируются отчеты о результатах тестирования с помощью checkstyle и pmd


