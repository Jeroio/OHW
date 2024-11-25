# Research-Institute

内容整理为Markdown格式，并在代码块中嵌套另一个代码块，并标注代码语言

Code:3000 Line

## 相关链接

- [博客园 - 开发者的网上家园](https://www.cnblogs.com/)
- [My IELTS](https://hefengxian.github.io/my-ielts/#/vocabulary)
- [GitHub](https://github.com/)
------
- [三星电子 香港 | 智能手机 | 电视 | 雪柜 洗衣机](https://www.samsung.com/hk/)
- [维基百科，自由的百科全书](https://zh.wikipedia.org/)
- [AITO 汽车 - 赛力斯华为联合设计](https://aito.auto/)
- [Microsoft Copilot: 你的 AI 助手](https://copilot.microsoft.com/)
------
- [混合信号和数字信号处理IC | Analog Devices](https://www.analog.com/cn/index.html)
- [Keysight 示波器](https://www.keysight.com.cn/cn/zh/products/oscilloscopes.html)
- [阻抗匹配与史密斯圆图](https://www.analog.com/cn/resources/technical-articles/impedance-matching-and-smith-chart-impedance-maxim-integrated.html)
------
- [分类:中华片-维基百科](https://zh.wikipedia.org/wiki/Category:%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%A6%81%E7%89%87)
------

## Python pip 配置

### 1. 查看 pip 源
```shell
pip config list
```

### 2. 查看 pip 源查找配置文件路径
```shell
pip -v config list
```

### 3. 更换 pip 源
```shell
pip config set global.index-url http://cmc-cd-mirror.rnd.huawei.com/pypi/simple
pip config set global.trusted-host cmc-cd-mirror.rnd.huawei.com
```
