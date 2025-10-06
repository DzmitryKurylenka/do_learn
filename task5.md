- name: Установка Nginx и обновление системы
  hosts: servers
  become: yes
  tasks:
    - name: Обновление системных пакетов
      apt:
        update_cache: yes
        upgrade: yes

    - name: Установка Nginx
      apt:
        name: nginx
        state: present

    - name: Изменение стандартной страницы Nginx
      copy:
        dest: /var/www/html/index.nginx-debian.html
        content: |
          <meta charset="UTF-8">
          <h1>Nginx установлен через Ansible</h1>