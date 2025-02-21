create user ravi as system account he should not have home directory
```
    1  adduser --help
    2  adduser --help | grep -E 'system|home'
    3  adduser ravi --system --no-create-home
    4  sudo adduser ravi --system --no-create-home
    5  id ravi
    6  cat /etc/passwd | grep ravi
    7  history
```
