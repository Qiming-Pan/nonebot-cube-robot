# 魔方打乱机器人-基于nonebot的机器人

#### 功能
- 运用nonebot模块，进行通信
- 无需进行修改操作，直接运行

#### 代码
**bot.py代码：**
```python
import nonebot
import config
from os import path


if __name__ == '__main__':
    nonebot.init(config)
    nonebot.load_plugins(
        path.join(path.dirname(__file__), 'awesome', 'plugins'),
        'awesome.plugins'
    )

    nonebot.run(host='127.0.0.1', port=8080)
```

**config.py代码：**
```python
from nonebot.default_config import *


SUPERUSERS = {2637087493}
COMMAND_START = {'.'}
```

#### 关于开源协议
禁止对代码进行商用，如果发现以法律解决

#### 图片（Pychram无法加载nonebot模块请忽略）
<img src="https://i.loli.net/2020/04/26/soiLEcJrnuIVTZN.jpg" width="40%"/>
