Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).



─(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ ansible-playbook role_globallyhub.yml

PLAY [Install Nginx] ***********************************************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 5.189.163.205 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Install absolute minimum Python dependencies (raw)] **************************************************************************************************************************************************************
^C [ERROR]: User interrupted execution
                                                                                                                                                                                                                                            
┌──(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ ansible-playbook role_globallyhub.yml

PLAY [Install Nginx] ***********************************************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 5.189.163.205 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Install absolute minimum Python dependencies (raw)] **************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Install cryptographic dependencies (raw)] ************************************************************************************************************************************************************************
^C [ERROR]: User interrupted execution
                                                                                                                                                                                                                                            
┌──(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ ansible-playbook role_globallyhub.yml

PLAY [Install Nginx] ***********************************************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 5.189.163.205 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Bootstrap Python environment (raw commands)] *********************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Pause to let system register changes] ****************************************************************************************************************************************************************************
Pausing for 10 seconds
(ctrl+C then 'C' = continue early, ctrl+C then 'A' = abort)
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Re-gather facts with new Python environment] *********************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Update all packages (using command module)] **********************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Install Nginx (using command module)] ****************************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Ensure Nginx is running] *****************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Creating Website directories in desired path] ********************************************************************************************************************************************************************
ok: [5.189.163.205] => (item=/var/www/task1)
ok: [5.189.163.205] => (item=/var/www/task2)

TASK [Globallyhub-Task2 : Create page1 content] ********************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Create page2 content] ********************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Configure nginx] *************************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Enable nginx site] ***********************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Configure UFW] ***************************************************************************************************************************************************************************************************
ok: [5.189.163.205] => (item=22)
ok: [5.189.163.205] => (item=80)
ok: [5.189.163.205] => (item=443)

TASK [Globallyhub-Task2 : Enable UFW] ******************************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Install via raw command] *****************************************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Run certbot] *****************************************************************************************************************************************************************************************************
FAILED - RETRYING: [5.189.163.205]: Run certbot (3 retries left).
FAILED - RETRYING: [5.189.163.205]: Run certbot (2 retries left).
FAILED - RETRYING: [5.189.163.205]: Run certbot (1 retries left).
fatal: [5.189.163.205]: FAILED! => {"attempts": 3, "changed": false, "cmd": ["certbot", "--nginx", "--non-interactive", "--agree-tos", "--redirect", "-m", "anishgharti.chhetry@gmail.com", "-d", "globallyhub.tezhni.com"], "delta": "0:00:00.295847", "end": "2025-04-06 10:17:00.435908", "msg": "non-zero return code", "rc": 1, "start": "2025-04-06 10:17:00.140061", "stderr": "Traceback (most recent call last):\n  File \"/usr/bin/certbot\", line 33, in <module>\n    sys.exit(load_entry_point('certbot==1.21.0', 'console_scripts', 'certbot')())\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/bin/certbot\", line 25, in importlib_load_entry_point\n    return next(matches).load()\n           ^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/metadata/__init__.py\", line 205, in load\n    module = import_module(match.group('module'))\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/__init__.py\", line 90, in import_module\n    return _bootstrap._gcd_import(name[level:], package, level)\n           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"<frozen importlib._bootstrap>\", line 1387, in _gcd_import\n  File \"<frozen importlib._bootstrap>\", line 1360, in _find_and_load\n  File \"<frozen importlib._bootstrap>\", line 1331, in _find_and_load_unlocked\n  File \"<frozen importlib._bootstrap>\", line 935, in _load_unlocked\n  File \"<frozen importlib._bootstrap_external>\", line 999, in exec_module\n  File \"<frozen importlib._bootstrap>\", line 488, in _call_with_frames_removed\n  File \"/usr/lib/python3/dist-packages/certbot/main.py\", line 2, in <module>\n    from certbot._internal import main as internal_main\n  File \"/usr/lib/python3/dist-packages/certbot/_internal/main.py\", line 17, in <module>\n    import josepy as jose\n  File \"/usr/lib/python3/dist-packages/josepy/__init__.py\", line 43, in <module>\n    from josepy.json_util import (\n  File \"/usr/lib/python3/dist-packages/josepy/json_util.py\", line 14, in <module>\n    from OpenSSL import crypto\n  File \"/usr/lib/python3/dist-packages/OpenSSL/__init__.py\", line 8, in <module>\n    from OpenSSL import crypto, SSL\n  File \"/usr/lib/python3/dist-packages/OpenSSL/crypto.py\", line 17, in <module>\n    from OpenSSL._util import (\n  File \"/usr/lib/python3/dist-packages/OpenSSL/_util.py\", line 6, in <module>\n    from cryptography.hazmat.bindings.openssl.binding import Binding\n  File \"/usr/lib/python3/dist-packages/cryptography/hazmat/bindings/openssl/binding.py\", line 14, in <module>\n    from cryptography.hazmat.bindings._openssl import ffi, lib\nModuleNotFoundError: No module named '_cffi_backend'", "stderr_lines": ["Traceback (most recent call last):", "  File \"/usr/bin/certbot\", line 33, in <module>", "    sys.exit(load_entry_point('certbot==1.21.0', 'console_scripts', 'certbot')())", "             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^", "  File \"/usr/bin/certbot\", line 25, in importlib_load_entry_point", "    return next(matches).load()", "           ^^^^^^^^^^^^^^^^^^^^", "  File \"/usr/lib/python3.12/importlib/metadata/__init__.py\", line 205, in load", "    module = import_module(match.group('module'))", "             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^", "  File \"/usr/lib/python3.12/importlib/__init__.py\", line 90, in import_module", "    return _bootstrap._gcd_import(name[level:], package, level)", "           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^", "  File \"<frozen importlib._bootstrap>\", line 1387, in _gcd_import", "  File \"<frozen importlib._bootstrap>\", line 1360, in _find_and_load", "  File \"<frozen importlib._bootstrap>\", line 1331, in _find_and_load_unlocked", "  File \"<frozen importlib._bootstrap>\", line 935, in _load_unlocked", "  File \"<frozen importlib._bootstrap_external>\", line 999, in exec_module", "  File \"<frozen importlib._bootstrap>\", line 488, in _call_with_frames_removed", "  File \"/usr/lib/python3/dist-packages/certbot/main.py\", line 2, in <module>", "    from certbot._internal import main as internal_main", "  File \"/usr/lib/python3/dist-packages/certbot/_internal/main.py\", line 17, in <module>", "    import josepy as jose", "  File \"/usr/lib/python3/dist-packages/josepy/__init__.py\", line 43, in <module>", "    from josepy.json_util import (", "  File \"/usr/lib/python3/dist-packages/josepy/json_util.py\", line 14, in <module>", "    from OpenSSL import crypto", "  File \"/usr/lib/python3/dist-packages/OpenSSL/__init__.py\", line 8, in <module>", "    from OpenSSL import crypto, SSL", "  File \"/usr/lib/python3/dist-packages/OpenSSL/crypto.py\", line 17, in <module>", "    from OpenSSL._util import (", "  File \"/usr/lib/python3/dist-packages/OpenSSL/_util.py\", line 6, in <module>", "    from cryptography.hazmat.bindings.openssl.binding import Binding", "  File \"/usr/lib/python3/dist-packages/cryptography/hazmat/bindings/openssl/binding.py\", line 14, in <module>", "    from cryptography.hazmat.bindings._openssl import ffi, lib", "ModuleNotFoundError: No module named '_cffi_backend'"], "stdout": "", "stdout_lines": []}       

TASK [Globallyhub-Task2 : Debug certbot failure] *******************************************************************************************************************************************************************************************
ok: [5.189.163.205] => {
    "msg": "Certbot failed with error: Traceback (most recent call last):\n  File \"/usr/bin/certbot\", line 33, in <module>\n    sys.exit(load_entry_point('certbot==1.21.0', 'console_scripts', 'certbot')())\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/bin/certbot\", line 25, in importlib_load_entry_point\n    return next(matches).load()\n           ^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/metadata/__init__.py\", line 205, in load\n    module = import_module(match.group('module'))\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/__init__.py\", line 90, in import_module\n    return _bootstrap._gcd_import(name[level:], package, level)\n           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"<frozen importlib._bootstrap>\", line 1387, in _gcd_import\n  File \"<frozen importlib._bootstrap>\", line 1360, in _find_and_load\n  File \"<frozen importlib._bootstrap>\", line 1331, in _find_and_load_unlocked\n  File \"<frozen importlib._bootstrap>\", line 935, in _load_unlocked\n  File \"<frozen importlib._bootstrap_external>\", line 999, in exec_module\n  File \"<frozen importlib._bootstrap>\", line 488, in _call_with_frames_removed\n  File \"/usr/lib/python3/dist-packages/certbot/main.py\", line 2, in <module>\n    from certbot._internal import main as internal_main\n  File \"/usr/lib/python3/dist-packages/certbot/_internal/main.py\", line 17, in <module>\n    import josepy as jose\n  File \"/usr/lib/python3/dist-packages/josepy/__init__.py\", line 43, in <module>\n    from josepy.json_util import (\n  File \"/usr/lib/python3/dist-packages/josepy/json_util.py\", line 14, in <module>\n    from OpenSSL import crypto\n  File \"/usr/lib/python3/dist-packages/OpenSSL/__init__.py\", line 8, in <module>\n    from OpenSSL import crypto, SSL\n  File \"/usr/lib/python3/dist-packages/OpenSSL/crypto.py\", line 17, in <module>\n    from OpenSSL._util import (\n  File \"/usr/lib/python3/dist-packages/OpenSSL/_util.py\", line 6, in <module>\n    from cryptography.hazmat.bindings.openssl.binding import Binding\n  File \"/usr/lib/python3/dist-packages/cryptography/hazmat/bindings/openssl/binding.py\", line 14, in <module>\n    from cryptography.hazmat.bindings._openssl import ffi, lib\nModuleNotFoundError: No module named '_cffi_backend'"                                                                                                                                                                                                                       
}

PLAY RECAP *********************************************************************************************************************************************************************************************************************************
5.189.163.205              : ok=16   changed=4    unreachable=0    failed=0    skipped=0    rescued=1    ignored=0   

                                                                                                                                                                                                                                            
┌──(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ 

this is my error


─(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ ansible-playbook role_globallyhub.yml

PLAY [Install Nginx] ***********************************************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 5.189.163.205 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Install absolute minimum Python dependencies (raw)] **************************************************************************************************************************************************************
^C [ERROR]: User interrupted execution
                                                                                                                                                                                                                                            
┌──(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ ansible-playbook role_globallyhub.yml

PLAY [Install Nginx] ***********************************************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 5.189.163.205 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Install absolute minimum Python dependencies (raw)] **************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Install cryptographic dependencies (raw)] ************************************************************************************************************************************************************************
^C [ERROR]: User interrupted execution
                                                                                                                                                                                                                                            
┌──(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ ansible-playbook role_globallyhub.yml

PLAY [Install Nginx] ***********************************************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 5.189.163.205 is using the discovered Python interpreter at /usr/bin/python3.12, but future installation of another Python interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-core/2.18/reference_appendices/interpreter_discovery.html for more information.
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Bootstrap Python environment (raw commands)] *********************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Pause to let system register changes] ****************************************************************************************************************************************************************************
Pausing for 10 seconds
(ctrl+C then 'C' = continue early, ctrl+C then 'A' = abort)
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Re-gather facts with new Python environment] *********************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Update all packages (using command module)] **********************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Install Nginx (using command module)] ****************************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Ensure Nginx is running] *****************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Creating Website directories in desired path] ********************************************************************************************************************************************************************
ok: [5.189.163.205] => (item=/var/www/task1)
ok: [5.189.163.205] => (item=/var/www/task2)

TASK [Globallyhub-Task2 : Create page1 content] ********************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Create page2 content] ********************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Configure nginx] *************************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Enable nginx site] ***********************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Configure UFW] ***************************************************************************************************************************************************************************************************
ok: [5.189.163.205] => (item=22)
ok: [5.189.163.205] => (item=80)
ok: [5.189.163.205] => (item=443)

TASK [Globallyhub-Task2 : Enable UFW] ******************************************************************************************************************************************************************************************************
ok: [5.189.163.205]

TASK [Globallyhub-Task2 : Install via raw command] *****************************************************************************************************************************************************************************************
changed: [5.189.163.205]

TASK [Globallyhub-Task2 : Run certbot] *****************************************************************************************************************************************************************************************************
FAILED - RETRYING: [5.189.163.205]: Run certbot (3 retries left).
FAILED - RETRYING: [5.189.163.205]: Run certbot (2 retries left).
FAILED - RETRYING: [5.189.163.205]: Run certbot (1 retries left).
fatal: [5.189.163.205]: FAILED! => {"attempts": 3, "changed": false, "cmd": ["certbot", "--nginx", "--non-interactive", "--agree-tos", "--redirect", "-m", "anishgharti.chhetry@gmail.com", "-d", "globallyhub.tezhni.com"], "delta": "0:00:00.295847", "end": "2025-04-06 10:17:00.435908", "msg": "non-zero return code", "rc": 1, "start": "2025-04-06 10:17:00.140061", "stderr": "Traceback (most recent call last):\n  File \"/usr/bin/certbot\", line 33, in <module>\n    sys.exit(load_entry_point('certbot==1.21.0', 'console_scripts', 'certbot')())\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/bin/certbot\", line 25, in importlib_load_entry_point\n    return next(matches).load()\n           ^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/metadata/__init__.py\", line 205, in load\n    module = import_module(match.group('module'))\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/__init__.py\", line 90, in import_module\n    return _bootstrap._gcd_import(name[level:], package, level)\n           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"<frozen importlib._bootstrap>\", line 1387, in _gcd_import\n  File \"<frozen importlib._bootstrap>\", line 1360, in _find_and_load\n  File \"<frozen importlib._bootstrap>\", line 1331, in _find_and_load_unlocked\n  File \"<frozen importlib._bootstrap>\", line 935, in _load_unlocked\n  File \"<frozen importlib._bootstrap_external>\", line 999, in exec_module\n  File \"<frozen importlib._bootstrap>\", line 488, in _call_with_frames_removed\n  File \"/usr/lib/python3/dist-packages/certbot/main.py\", line 2, in <module>\n    from certbot._internal import main as internal_main\n  File \"/usr/lib/python3/dist-packages/certbot/_internal/main.py\", line 17, in <module>\n    import josepy as jose\n  File \"/usr/lib/python3/dist-packages/josepy/__init__.py\", line 43, in <module>\n    from josepy.json_util import (\n  File \"/usr/lib/python3/dist-packages/josepy/json_util.py\", line 14, in <module>\n    from OpenSSL import crypto\n  File \"/usr/lib/python3/dist-packages/OpenSSL/__init__.py\", line 8, in <module>\n    from OpenSSL import crypto, SSL\n  File \"/usr/lib/python3/dist-packages/OpenSSL/crypto.py\", line 17, in <module>\n    from OpenSSL._util import (\n  File \"/usr/lib/python3/dist-packages/OpenSSL/_util.py\", line 6, in <module>\n    from cryptography.hazmat.bindings.openssl.binding import Binding\n  File \"/usr/lib/python3/dist-packages/cryptography/hazmat/bindings/openssl/binding.py\", line 14, in <module>\n    from cryptography.hazmat.bindings._openssl import ffi, lib\nModuleNotFoundError: No module named '_cffi_backend'", "stderr_lines": ["Traceback (most recent call last):", "  File \"/usr/bin/certbot\", line 33, in <module>", "    sys.exit(load_entry_point('certbot==1.21.0', 'console_scripts', 'certbot')())", "             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^", "  File \"/usr/bin/certbot\", line 25, in importlib_load_entry_point", "    return next(matches).load()", "           ^^^^^^^^^^^^^^^^^^^^", "  File \"/usr/lib/python3.12/importlib/metadata/__init__.py\", line 205, in load", "    module = import_module(match.group('module'))", "             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^", "  File \"/usr/lib/python3.12/importlib/__init__.py\", line 90, in import_module", "    return _bootstrap._gcd_import(name[level:], package, level)", "           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^", "  File \"<frozen importlib._bootstrap>\", line 1387, in _gcd_import", "  File \"<frozen importlib._bootstrap>\", line 1360, in _find_and_load", "  File \"<frozen importlib._bootstrap>\", line 1331, in _find_and_load_unlocked", "  File \"<frozen importlib._bootstrap>\", line 935, in _load_unlocked", "  File \"<frozen importlib._bootstrap_external>\", line 999, in exec_module", "  File \"<frozen importlib._bootstrap>\", line 488, in _call_with_frames_removed", "  File \"/usr/lib/python3/dist-packages/certbot/main.py\", line 2, in <module>", "    from certbot._internal import main as internal_main", "  File \"/usr/lib/python3/dist-packages/certbot/_internal/main.py\", line 17, in <module>", "    import josepy as jose", "  File \"/usr/lib/python3/dist-packages/josepy/__init__.py\", line 43, in <module>", "    from josepy.json_util import (", "  File \"/usr/lib/python3/dist-packages/josepy/json_util.py\", line 14, in <module>", "    from OpenSSL import crypto", "  File \"/usr/lib/python3/dist-packages/OpenSSL/__init__.py\", line 8, in <module>", "    from OpenSSL import crypto, SSL", "  File \"/usr/lib/python3/dist-packages/OpenSSL/crypto.py\", line 17, in <module>", "    from OpenSSL._util import (", "  File \"/usr/lib/python3/dist-packages/OpenSSL/_util.py\", line 6, in <module>", "    from cryptography.hazmat.bindings.openssl.binding import Binding", "  File \"/usr/lib/python3/dist-packages/cryptography/hazmat/bindings/openssl/binding.py\", line 14, in <module>", "    from cryptography.hazmat.bindings._openssl import ffi, lib", "ModuleNotFoundError: No module named '_cffi_backend'"], "stdout": "", "stdout_lines": []}       

TASK [Globallyhub-Task2 : Debug certbot failure] *******************************************************************************************************************************************************************************************
ok: [5.189.163.205] => {
    "msg": "Certbot failed with error: Traceback (most recent call last):\n  File \"/usr/bin/certbot\", line 33, in <module>\n    sys.exit(load_entry_point('certbot==1.21.0', 'console_scripts', 'certbot')())\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/bin/certbot\", line 25, in importlib_load_entry_point\n    return next(matches).load()\n           ^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/metadata/__init__.py\", line 205, in load\n    module = import_module(match.group('module'))\n             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"/usr/lib/python3.12/importlib/__init__.py\", line 90, in import_module\n    return _bootstrap._gcd_import(name[level:], package, level)\n           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^\n  File \"<frozen importlib._bootstrap>\", line 1387, in _gcd_import\n  File \"<frozen importlib._bootstrap>\", line 1360, in _find_and_load\n  File \"<frozen importlib._bootstrap>\", line 1331, in _find_and_load_unlocked\n  File \"<frozen importlib._bootstrap>\", line 935, in _load_unlocked\n  File \"<frozen importlib._bootstrap_external>\", line 999, in exec_module\n  File \"<frozen importlib._bootstrap>\", line 488, in _call_with_frames_removed\n  File \"/usr/lib/python3/dist-packages/certbot/main.py\", line 2, in <module>\n    from certbot._internal import main as internal_main\n  File \"/usr/lib/python3/dist-packages/certbot/_internal/main.py\", line 17, in <module>\n    import josepy as jose\n  File \"/usr/lib/python3/dist-packages/josepy/__init__.py\", line 43, in <module>\n    from josepy.json_util import (\n  File \"/usr/lib/python3/dist-packages/josepy/json_util.py\", line 14, in <module>\n    from OpenSSL import crypto\n  File \"/usr/lib/python3/dist-packages/OpenSSL/__init__.py\", line 8, in <module>\n    from OpenSSL import crypto, SSL\n  File \"/usr/lib/python3/dist-packages/OpenSSL/crypto.py\", line 17, in <module>\n    from OpenSSL._util import (\n  File \"/usr/lib/python3/dist-packages/OpenSSL/_util.py\", line 6, in <module>\n    from cryptography.hazmat.bindings.openssl.binding import Binding\n  File \"/usr/lib/python3/dist-packages/cryptography/hazmat/bindings/openssl/binding.py\", line 14, in <module>\n    from cryptography.hazmat.bindings._openssl import ffi, lib\nModuleNotFoundError: No module named '_cffi_backend'"                                                                                                                                                                                                                       
}

PLAY RECAP *********************************************************************************************************************************************************************************************************************************
5.189.163.205              : ok=16   changed=4    unreachable=0    failed=0    skipped=0    rescued=1    ignored=0   

                                                                                                                                                                                                                                            
┌──(anishchengre㉿msiGL63Rd)-[~/.ansible/playbooks]
└─$ 
 they are my folders under roles and 

---

- name: Bootstrap Python environment (raw commands)
  raw: |
    sudo apt-get update
    sudo apt-get install -y python3 python3-apt python3-distutils
  args:
    executable: /bin/bash
  register: bootstrap
  changed_when: bootstrap.stdout != ''

- name: Pause to let system register changes
  pause:
    seconds: 10

- name: Re-gather facts with new Python environment
  setup:

- name: Update all packages (using command module)
  command: sudo apt-get dist-upgrade -y
  register: upgrade
  changed_when: upgrade.stdout != ''

- name: Install Nginx (using command module)
  command: sudo apt-get install -y nginx
  when: ansible_facts.python.version.major == 3

- name: Ensure Nginx is running
  service:
    name: nginx
    state: started
    enabled: yes
  become: true



#...
- name: Creating Website directories in desired path
  file:
    path: "{{ item }}"
    state: directory
    owner: anishchengre
    group: anishchengre
    mode: '0755'
  loop:
    - /var/www/task1  
    - /var/www/task2
  become: true  # Add this to run with sudo

- name: Create page1 content
  copy:
    content: "<h1>Page 1 Content</h1>"
    dest: /var/www/task1/index.html
    owner: anishchengre
    group: anishchengre
    mode: '0644'      
  become: true  # Add this to run with sudo


- name: Create page2 content
  copy:
    content: "<h1>Page 2 Content</h1>"
    dest: /var/www/task2/index.html
    owner: anishchengre
    group: anishchengre
    mode: '0644'
  become: true  # Add this to run with sudo



- name: Configure nginx 
  template:
    src: nginx_config.j2
    dest: /etc/nginx/sites-available/GloballyHub
  notify: Reload Nginx  
  become: true  # This was missing


- name: Enable nginx site
  file:
    src: /etc/nginx/sites-available/GloballyHub
    dest: /etc/nginx/sites-enabled/GloballyHub
    state: link
  notify: Reload Nginx    
  become: true  # This was missing


- name: Configure UFW
  ufw:
    rule: allow
    port: "{{ item }}"
  loop:
    - "22"
    - "80"  
    - "443"  

  notify: Reload UFW  
  become: true  # This was missing


- name: Enable UFW
  ufw:
    state: enabled
    default: deny
  become: true  # This was missing

# Certbot installation
- name: Install certbot and dependencies
  block:
    - name: Install via raw command
      raw: |
        sudo apt-get update
        sudo apt-get install -y certbot python3-certbot-nginx
      args:
        executable: /bin/bash
      register: certbot_install
      changed_when: certbot_install.stdout != ''
      become: true

  rescue:
    - name: Fallback manual installation
      debug:
        msg: "Failed to install certbot automatically. Please run manually: sudo apt-get install -y certbot python3-certbot-nginx"

   # SSL Certificate generation
- name: Generate SSL Certificate
  block:
    - name: Run certbot
      command:
        cmd: "certbot --nginx --non-interactive --agree-tos --redirect -m {{ certbot_email }} -d {{ certbot_domain }}"
      register: certbot_output
      retries: 3
      delay: 10
      until: "'Congratulations' in certbot_output.stdout"
      changed_when: "'Congratulations' in certbot_output.stdout"
      become: true
      when: certbot_email is defined

  rescue:
    - name: Debug certbot failure
      debug:
        msg: "Certbot failed with error: {{ certbot_output.stderr }}"

 ad this is the content of main.yml of task


---
# handlers/main.yml
- name: Reload Nginx
  service:
    name: nginx
    state: reloaded
  become: true

- name: Reload ufw
  service:
    name: ufw
    state: reloaded
  become: true  and thisis inside handler/main.yml
canu solve the error and  rewrite the whole code in task/main.yml so that i can copy and paste and when installing dont use apt cause it is givingmy python error so donwload from raw command