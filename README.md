```
Лаб 3. Ansible, работа с переменными и циклами

```

```
Сделать ansible-плейбук, который на целевых хостах:

устанавливает сканер NMAP
разбирает файл с целями на список и отдаёт цели на сканер в цикле
запускает NMAP и сканирует цели с ключом -p 80 (в цикле)
Собирает результаты сканирования (stdout)
выводит результаты сканирования на экран.
Результаты оформить в гит репо и выложить на github.

В качестве ответа прикрепить ссылку на github репо.
```

```
Результаты
```
```
PLAY [Scan targets] ************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************
ok: [10.0.2.17]
ok: [10.0.2.16]

TASK [Ensure NMAP installed] ***************************************************************************************************
ok: [10.0.2.16]
ok: [10.0.2.17]

TASK [Scan] ********************************************************************************************************************
changed: [10.0.2.17] => (item=moodle-epos.permkrai.ru)
changed: [10.0.2.16] => (item=moodle-epos.permkrai.ru)
changed: [10.0.2.17] => (item=www.psu.ru)
changed: [10.0.2.16] => (item=www.psu.ru)
changed: [10.0.2.16] => (item=fast.com)
changed: [10.0.2.17] => (item=fast.com)

TASK [Scan result] *************************************************************************************************************
ok: [10.0.2.16] => (item={'changed': True, 'stdout': '# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - moodle-epos.permkrai.ru\nHost: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tStatus: Up\nHost: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///\n# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds', 'stderr': '', 'rc': 0, 'cmd': ['nmap', 'moodle-epos.permkrai.ru', '-p', '80,443', '-oG', '-'], 'start': '2025-06-28 15:13:47.017217', 'end': '2025-06-28 15:13:47.108703', 'delta': '0:00:00.091486', 'msg': '', 'invocation': {'module_args': {'_raw_params': 'nmap moodle-epos.permkrai.ru -p 80,443 -oG -', '_uses_shell': False, 'expand_argument_vars': True, 'stdin_add_newline': True, 'strip_empty_ends': True, 'argv': None, 'chdir': None, 'executable': None, 'creates': None, 'removes': None, 'stdin': None}}, 'stdout_lines': ['# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - moodle-epos.permkrai.ru', 'Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tStatus: Up', 'Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///', '# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds'], 'stderr_lines': [], 'failed': False, 'item': 'moodle-epos.permkrai.ru', 'ansible_loop_var': 'item'}) => {
    "msg": [
        "# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - moodle-epos.permkrai.ru",
        "Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tStatus: Up",
        "Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///",
        "# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds"
    ]
}
ok: [10.0.2.16] => (item={'changed': True, 'stdout': '# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - www.psu.ru\nHost: 212.192.64.44 (www.psu.ru)\tStatus: Up\nHost: 212.192.64.44 (www.psu.ru)\tPorts: 80/open/tcp//http///, 443/closed/tcp//https///\n# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds', 'stderr': '', 'rc': 0, 'cmd': ['nmap', 'www.psu.ru', '-p', '80,443', '-oG', '-'], 'start': '2025-06-28 15:13:47.350800', 'end': '2025-06-28 15:13:47.436680', 'delta': '0:00:00.085880', 'msg': '', 'invocation': {'module_args': {'_raw_params': 'nmap www.psu.ru -p 80,443 -oG -', '_uses_shell': False, 'expand_argument_vars': True, 'stdin_add_newline': True, 'strip_empty_ends': True, 'argv': None, 'chdir': None, 'executable': None, 'creates': None, 'removes': None, 'stdin': None}}, 'stdout_lines': ['# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - www.psu.ru', 'Host: 212.192.64.44 (www.psu.ru)\tStatus: Up', 'Host: 212.192.64.44 (www.psu.ru)\tPorts: 80/open/tcp//http///, 443/closed/tcp//https///', '# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds'], 'stderr_lines': [], 'failed': False, 'item': 'www.psu.ru', 'ansible_loop_var': 'item'}) => {
    "msg": [
        "# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - www.psu.ru",
        "Host: 212.192.64.44 (www.psu.ru)\tStatus: Up",
        "Host: 212.192.64.44 (www.psu.ru)\tPorts: 80/open/tcp//http///, 443/closed/tcp//https///",
        "# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds"
    ]
}
ok: [10.0.2.17] => (item={'changed': True, 'stdout': '# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - moodle-epos.permkrai.ru\nHost: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tStatus: Up\nHost: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///\n# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds', 'stderr': '', 'rc': 0, 'cmd': ['nmap', 'moodle-epos.permkrai.ru', '-p', '80,443', '-oG', '-'], 'start': '2025-06-28 15:13:47.009384', 'end': '2025-06-28 15:13:47.097800', 'delta': '0:00:00.088416', 'msg': '', 'invocation': {'module_args': {'_raw_params': 'nmap moodle-epos.permkrai.ru -p 80,443 -oG -', '_uses_shell': False, 'expand_argument_vars': True, 'stdin_add_newline': True, 'strip_empty_ends': True, 'argv': None, 'chdir': None, 'executable': None, 'creates': None, 'removes': None, 'stdin': None}}, 'stdout_lines': ['# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - moodle-epos.permkrai.ru', 'Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tStatus: Up', 'Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///', '# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds'], 'stderr_lines': [], 'failed': False, 'item': 'moodle-epos.permkrai.ru', 'ansible_loop_var': 'item'}) => {
    "msg": [
        "# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - moodle-epos.permkrai.ru",
        "Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tStatus: Up",
        "Host: 212.33.224.15 (212.33.224.15.static-business.perm.ertelecom.ru)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///",
        "# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds"
    ]
}
ok: [10.0.2.16] => (item={'changed': True, 'stdout': '# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - fast.com\nHost: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tStatus: Up\nHost: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///\n# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.10 seconds', 'stderr': '', 'rc': 0, 'cmd': ['nmap', 'fast.com', '-p', '80,443', '-oG', '-'], 'start': '2025-06-28 15:13:47.647799', 'end': '2025-06-28 15:13:47.751405', 'delta': '0:00:00.103606', 'msg': '', 'invocation': {'module_args': {'_raw_params': 'nmap fast.com -p 80,443 -oG -', '_uses_shell': False, 'expand_argument_vars': True, 'stdin_add_newline': True, 'strip_empty_ends': True, 'argv': None, 'chdir': None, 'executable': None, 'creates': None, 'removes': None, 'stdin': None}}, 'stdout_lines': ['# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - fast.com', 'Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tStatus: Up', 'Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///', '# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.10 seconds'], 'stderr_lines': [], 'failed': False, 'item': 'fast.com', 'ansible_loop_var': 'item'}) => {
    "msg": [
        "# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - fast.com",
        "Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tStatus: Up",
        "Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///",
        "# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.10 seconds"
    ]
}
ok: [10.0.2.17] => (item={'changed': True, 'stdout': '# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - www.psu.ru\nHost: 212.192.64.44 (www.psu.ru)\tStatus: Up\nHost: 212.192.64.44 (www.psu.ru)\tPorts: 80/open/tcp//http///, 443/closed/tcp//https///\n# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds', 'stderr': '', 'rc': 0, 'cmd': ['nmap', 'www.psu.ru', '-p', '80,443', '-oG', '-'], 'start': '2025-06-28 15:13:47.345563', 'end': '2025-06-28 15:13:47.428979', 'delta': '0:00:00.083416', 'msg': '', 'invocation': {'module_args': {'_raw_params': 'nmap www.psu.ru -p 80,443 -oG -', '_uses_shell': False, 'expand_argument_vars': True, 'stdin_add_newline': True, 'strip_empty_ends': True, 'argv': None, 'chdir': None, 'executable': None, 'creates': None, 'removes': None, 'stdin': None}}, 'stdout_lines': ['# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - www.psu.ru', 'Host: 212.192.64.44 (www.psu.ru)\tStatus: Up', 'Host: 212.192.64.44 (www.psu.ru)\tPorts: 80/open/tcp//http///, 443/closed/tcp//https///', '# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds'], 'stderr_lines': [], 'failed': False, 'item': 'www.psu.ru', 'ansible_loop_var': 'item'}) => {
    "msg": [
        "# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - www.psu.ru",
        "Host: 212.192.64.44 (www.psu.ru)\tStatus: Up",
        "Host: 212.192.64.44 (www.psu.ru)\tPorts: 80/open/tcp//http///, 443/closed/tcp//https///",
        "# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.08 seconds"
    ]
}
ok: [10.0.2.17] => (item={'changed': True, 'stdout': '# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - fast.com\nHost: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tStatus: Up\nHost: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///\n# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.10 seconds', 'stderr': '', 'rc': 0, 'cmd': ['nmap', 'fast.com', '-p', '80,443', '-oG', '-'], 'start': '2025-06-28 15:13:47.640427', 'end': '2025-06-28 15:13:47.751965', 'delta': '0:00:00.111538', 'msg': '', 'invocation': {'module_args': {'_raw_params': 'nmap fast.com -p 80,443 -oG -', '_uses_shell': False, 'expand_argument_vars': True, 'stdin_add_newline': True, 'strip_empty_ends': True, 'argv': None, 'chdir': None, 'executable': None, 'creates': None, 'removes': None, 'stdin': None}}, 'stdout_lines': ['# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - fast.com', 'Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tStatus: Up', 'Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///', '# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.10 seconds'], 'stderr_lines': [], 'failed': False, 'item': 'fast.com', 'ansible_loop_var': 'item'}) => {
    "msg": [
        "# Nmap 7.94SVN scan initiated Sat Jun 28 15:13:47 2025 as: nmap -p 80,443 -oG - fast.com",
        "Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tStatus: Up",
        "Host: 88.221.96.195 (a88-221-96-195.deploy.static.akamaitechnologies.com)\tPorts: 80/open/tcp//http///, 443/open/tcp//https///",
        "# Nmap done at Sat Jun 28 15:13:47 2025 -- 1 IP address (1 host up) scanned in 0.10 seconds"
    ]
}

PLAY RECAP *********************************************************************************************************************
10.0.2.16                  : ok=4    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
10.0.2.17                  : ok=4    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```
