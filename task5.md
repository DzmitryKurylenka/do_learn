- name: ��������� Nginx � ���������� �������
  hosts: servers
  become: yes
  tasks:
    - name: ���������� ��������� �������
      apt:
        update_cache: yes
        upgrade: yes

    - name: ��������� Nginx
      apt:
        name: nginx
        state: present

    - name: ��������� ����������� �������� Nginx
      copy:
        dest: /var/www/html/index.nginx-debian.html
        content: |
          <meta charset="UTF-8">
          <h1>Nginx ���������� ����� Ansible</h1>