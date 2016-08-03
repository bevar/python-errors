## 目录

* [ImportError: libmysqlclient.so.18: cannot open shared object file: No such file or directory" happens when "import MySQLdb](### 1. "ImportError: libmysqlclient.so.18: cannot open shared object file: No such file or directory" happens when "import MySQLdb")


### 1. "ImportError: libmysqlclient.so.18: cannot open shared object file: No such file or directory" happens when "import MySQLdb"

描述： 系统从ubuntu 15升级到ubuntu 16.04，当*import MySQLdb*时会抛出这个异
常，重新卸载mysql-python，再安装也无济于事。

原因分析： 升级系统同时也升级了MySQL，但是对应的mysql-python并没有改变，可能
mysql-python引用了某个较老版本的库文件，更新系统时这个库文件被更新了，这时
就需要重新安装mysql-python来解决问题，但是你卸载掉mysql-python再重新安装很
有可能从当前缓存里面又安装了原来一样的，所以这时你需要禁用缓存。

解决办法:

```shell
pip uninstall mysql-python
pip install --no-cache-dir mysql-python
# --no-cache-dir十分重要
```
