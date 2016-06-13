## Platforms
OS: ubuntu 16.04

Python: 2.7.10

MySQL: 5.7.12

If no special explanation, these are default platforms.

### 1. "ImportError: libmysqlclient.so.18: cannot open shared object file: No such file or directory" happens when "import MySQLdb"

After I upgraded my ubuntu from 15 to 16.04, this ImportError was shown when I "import MySQLdb".

Solution:
```shell
sudo pip uninstall mysql-python
sudo pip install --no-cache-dir mysql-python
# no-cache-dir is very important, if you don't pass this argument, you'll still get this error.
```
