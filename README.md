## Домашнее задание к занятию "8.4 Работа с Roles"
### Подготовка к выполнению
Создайте два пустых публичных репозитория в любом своём проекте: kibana-role и filebeat-role.
Добавьте публичную часть своего ключа к своему профилю в github.
###Основная часть
Наша основная цель - разбить наш playbook на отдельные roles. Задача: сделать roles для elastic, kibana, filebeat и написать playbook для использования этих ролей. Ожидаемый результат: существуют два ваших репозитория с roles и один репозиторий с playbook.

##### 1.Создать в старой версии playbook файл requirements.yml и заполнить его следующим содержимым:

    ---
      - src: git@github.com:netology-code/mnt-homeworks-ansible.git
        scm: git
        version: "2.0.0"
        name: elastic

    
#### 2.При помощи ansible-galaxy скачать себе эту роль.

    vagrant@vagrant:~/gitwork/8.4-roles$ ansible-galaxy install -r requirements.yml
    Starting galaxy role install process
    - extracting filebeat to /home/vagrant/.ansible/roles/elastic
    - elastic was installed successfully

#### 3.Создать новый каталог с ролью при помощи ansible-galaxy role init kibana-role.
    
    ├── kibana-role
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── README.md
    │   ├── tasks
    │   │   ├── configure.yml
    │   │   ├── download_apt.yml
    │   │   ├── download_yum.yml
    │   │   ├── install_apt.yml
    │   │   ├── install_yum.yml
    │   │   ├── main.yml
    │   │   └── precheck.yml
    │   ├── templates
    │   │   └── kibana.yml.j2
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
#### 4.На основе tasks из старого playbook заполните новую role. Разнесите переменные между vars и default.
#### 5.Перенести нужные шаблоны конфигов в templates.
#### 6.Создать новый каталог с ролью при помощи ansible-galaxy role init filebeat-role.
    
    ├── filebeat-role
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── README.md
    │   ├── tasks
    │   │   ├── configure.yml
    │   │   ├── download_apt.yml
    │   │   ├── download_yum.yml
    │   │   ├── install_apt.yml
    │   │   ├── install_yum.yml
    │   │   ├── main.yml
    │   │   └── precheck.yml
    │   ├── templates
    │   │   └── filebeat.yml.j2
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
#### 7.На основе tasks из старого playbook заполните новую role. Разнесите переменные между vars и default.
#### 8.Перенести нужные шаблоны конфигов в templates.
#### 9.Описать в README.md обе роли и их параметры.
#### 10.Выложите все roles в репозитории. Проставьте тэги, используя семантическую нумерацию.
#### 11.Добавьте roles в requirements.yml в playbook.
#### 12.Переработайте playbook на использование roles.
#### 13 Выложите playbook в репозиторий.
  
#### 14. В ответ приведите ссылки на оба репозитория с roles и одну ссылку на репозиторий с playbook.
    
    Filebeat role https://github.com/andrey-grozov/filebeat-role.git

    Kibana role https://github.com/andrey-grozov/kibana-role.git

    Playbook https://github.com/andrey-grozov/8.4-roles.git