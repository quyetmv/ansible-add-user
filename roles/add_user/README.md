Uers role DEMO
==========

- Role to manage users on a system.

- Nên sử dụng biến `users: [quyetmv', 'xxxx']` trong host_vars ( nếu muốn thêm từng các user khác nhau cho từng host khác nhau ) hoặc group_vars

- Khi muốn xóa một user ra khỏi hệ thống. Sử dụng biến `users_deleted: ['quyetmv']` và chạy lại role này. User đó sẽ được xóa.



Default Variables
-----------------

```
users_default_shell: /bin/bash
users_create_homedirs: true
```

Example Playbook
----------------

```
# Essential Task, need to run on all node
- hosts: new
  remote_user: root
  vars:
    users: ['quyetmv', 'xxx']
    users_deleted: ['quyetmv']
  roles:
    - users
```
