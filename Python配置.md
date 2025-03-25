## Python pip 配置

### 1. 查看 pip 源
```shell
pip config list
```

### 2. 查看 pip 源查找配置文件路径
```bash
pip -v config list
```

### 3. 更换 pip 源
```bash
pip config set global.index-url http://cmc-cd-mirror.rnd.huawei.com/pypi/simple
pip config set global.trusted-host cmc-cd-mirror.rnd.huawei.com
```