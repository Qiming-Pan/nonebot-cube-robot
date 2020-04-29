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


**cube.py代码**
```python
from nonebot import on_command, CommandSession
from random import choice


def three():
    TURN_333 = ("U","R","F","D","L","B","U2","R2","F2","D2","L2","B2","U'","R'","F'","D'","L'","B'")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 20
    count = 0
    while count < LENGTH:
        turn = choice(TURN_333)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            continue
        elif turn.find("F") == 0 and pre_turn.find("F") == 0:
            continue
        elif turn.find("D") == 0 and pre_turn.find("D") == 0:
            continue
        elif turn.find("L") == 0 and pre_turn.find("L") == 0:
            continue
        elif turn.find("B") == 0 and pre_turn.find("B") == 0:
            continue
        else:
            scb += turn +' '
            pre_turn = turn
            count += 1
    return scb      


def two():
    TURN_222 = ("U", "R", "F", "U'", "R'", "F", "U2", "R2", "F2")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 9
    count =0 
    while count < LENGTH:
        turn = choice(TURN_222)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            continue
        elif turn.find("F") == 0 and pre_turn.find("F")  == 0:
            continue
        else:
            scb += turn +' '
            pre_turn =turn
            count += 1
    return scb
  

def four():
    TURN_444 = ("U" , "U2" , "Uw" , "Uw2" ,"U'" ,"Uw'" , "R" , "R2" , "Rw" , "Rw2" ,"R'" ,"Rw'" , "F" , "F2" , "Fw" , "Fw2" ,"F'" ,"Fw'" , "B" , "B2" , "Bw" , "Bw2" ,"B'" ,"Bw'" , "L" , "L2" , "Lw" , "Lw2" ,"L'" ,"Lw'" , "D" , "D2" , "Dw" , "Dw2" ,"D'" ,"Dw'")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 50
    count =0 
    while count < LENGTH:
        turn = choice(TURN_444)
        #允许[true]w[rev]与[true]连续出现
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("F") == 0 and pre_turn.find("F")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("B") == 0 and pre_turn.find("B")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("L") == 0 and pre_turn.find("L")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("D") == 0 and pre_turn.find("D")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        else :
            scb += turn +' '
            pre_turn =turn
            count += 1
    return scb


def five():
    TURN_555 = ("U", "U2", "Uw", "Uw2", "U'", "Uw'", "R", "R2", "Rw", "Rw2", "R'", "Rw'", "F", "F2", "Fw", "Fw2", "F'", "Fw'", "B","B2", "Bw", "Bw2", "B'", "Bw'", "L", "L2", "Lw", "Lw2", "L'", "Lw'", "D", "D2", "Dw", "Dw2", "D'", "Dw'")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 60
    count =0 
    while count < LENGTH:
        turn = choice(TURN_555)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("F") == 0 and pre_turn.find("F")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("B") == 0 and pre_turn.find("B")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("L") == 0 and pre_turn.find("L")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        elif turn.find("D") == 0 and pre_turn.find("D")  == 0:
            if turn.find("w") == 0 and pre_turn.find("w") == -1  or pre_turn.find("w") == 0 and turn.find("w") == -1:
                scb += turn + ' '
                pre_turn = turn
                count += 1
            else:
                continue
        else :
            scb += turn +' '
            pre_turn =turn
            count += 1
    return scb


def six():
    TURN_666 = ("U","U2","3Uw","Uw","3Uw2","Uw2","U'","3Uw'","Uw'","R","R'","R2","3Rw","Rw","Rw'","3Rw'","3Rw2","Rw2","F","F'","F2","3Fw","3Fw'","3Fw2","Fw","Fw'","Fw2","L","L2","L'","3Lw","3Lw2","3Lw'","L" "L2" , "Lw" , "Lw2" ,"L'" ,"Lw'" , "D" , "D2" , "Dw" , "Dw2" ,"D'" ,"Dw'")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 80
    count =0
    while count < LENGTH:
        turn = choice(TURN_666)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            continue
        elif turn.find("F") == 0 and pre_turn.find("F") == 0:
            continue
        elif turn.find("D") == 0 and pre_turn.find("D") == 0:
            continue
        elif turn.find("L") == 0 and pre_turn.find("L") == 0:
            continue
        elif turn.find("B") == 0 and pre_turn.find("B") == 0:
            continue
        else:
            scb += turn +' '
            pre_turn = turn
            count += 1
    return scb        


def seven():
    TURN_777 = ("U","U2","3Uw","Uw","3Uw2","Uw2","U'","3Uw'","Uw'","R","R'","R2","3Rw","Rw","Rw'","3Rw'","3Rw2","Rw2","F","F'","F2","3Fw","3Fw'","3Fw2","Fw","Fw'","Fw2","L","L2","L'","3Lw","3Lw2","3Lw'","Lw","Lw'","Lw2","D","D2","D'","Dw","Dw2","Dw'","3Dw","3Dw'","3Dw2","B","B2","B'","3Bw","3Bw2","3Bw'","Bw","Bw'","Bw2")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 100
    count =0
    while count < LENGTH:
        turn = choice(TURN_777)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            continue
        elif turn.find("F") == 0 and pre_turn.find("F") == 0:
            continue
        elif turn.find("D") == 0 and pre_turn.find("D") == 0:
            continue
        elif turn.find("L") == 0 and pre_turn.find("L") == 0:
            continue
        elif turn.find("B") == 0 and pre_turn.find("B") == 0:
            continue
        else:
            scb += turn +' '
            pre_turn = turn
            count += 1
    return scb


def leaves():
    TURN_leaves = ("U","R","F","D","L","B","U2","R2","F2","D2","L2","B2","U'","R'","F'","D'","L'","B'")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 6
    count = 0
    while count < LENGTH:
        turn = choice(TURN_leaves)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            continue
        elif turn.find("F") == 0 and pre_turn.find("F") == 0:
            continue
        elif turn.find("D") == 0 and pre_turn.find("D") == 0:
            continue
        elif turn.find("L") == 0 and pre_turn.find("L") == 0:
            continue
        elif turn.find("B") == 0 and pre_turn.find("B") == 0:
            continue
        else:
            scb += turn +' '
            pre_turn = turn
            count += 1
    return scb  


def skewb():
    TURN_skewb = ("U","R","F","D","L","B","U2","R2","F2","D2","L2","B2","U'","R'","F'","D'","L'","B'")
    pre_turn = ''
    turn = ''
    scb = ''
    LENGTH = 9
    count = 0
    while count < LENGTH:
        turn = choice(TURN_skewb)
        if turn.find("U") == 0 and pre_turn.find("U") == 0:
            continue
        elif turn.find("R") == 0 and pre_turn.find("R") == 0:
            continue
        elif turn.find("F") == 0 and pre_turn.find("F") == 0:
            continue
        elif turn.find("D") == 0 and pre_turn.find("D") == 0:
            continue
        elif turn.find("L") == 0 and pre_turn.find("L") == 0:
            continue
        elif turn.find("B") == 0 and pre_turn.find("B") == 0:
            continue
        else:
            scb += turn +' '
            pre_turn = turn
            count += 1
    return scb 


e = ['R++ ','R-- ']
f = ['D++ ','D-- ']
g = ['D++ U ','D-- U’']
minx = e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]+'\n'+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]+'\n'+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]+'\n'+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]+'\n'+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]+'\n'+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]+'\n'+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+f[randint(0,1)]+e[randint(0,1)]+g[randint(0,1)]


a = ['1','2','3','4','5','6']
b = ['+','-']
c = ['0','1','2','3','4','5','6']
d = ['DR''DL','UR','UL','DR DL','DR UR','DR UL','DL DR','DL UR','DL UL','UR DR','UR DL','UR UL','UL DR','UL DL','UL UR']
clock = 'UR'+a[randint(0,5)]+b[randint(0,1)]+' DR'+a[randint(0,5)]+b[randint(0,1)]+' DL'+a[randint(0,5)]+b[randint(0,1)]+' UL'+a[randint(0,5)]+b[randint(0,1)]+' U'+a[randint(0,5)]+b[randint(0,1)]+' R'+a[randint(0,5)]+b[randint(0,1)]+' D'+a[randint(0,5)]+b[randint(0,1)]+' L'+a[randint(0,5)]+b[randint(0,1)]+' ALL'+a[randint(0,5)]+' y2'+' U'+c[randint(0,6)]+b[randint(0,1)]+' R'+c[randint(0,6)]+b[randint(0,1)]+' D'+c[randint(0,6)]+b[randint(0,1)]+' L'+c[randint(0,6)]+b[randint(0,1)]+' ALL'+a[randint(0,5)]+b[randint(0,1)]+d[randint(0,13)]


@on_command('three',aliases=('3','333','3*3*3'),only_to_me=False)
async def threesend(session: CommandSession):
    await session.send('3*3*3\n'+three())


@on_command('two',aliases=('2','222','2*2*2'),only_to_me=False)
async def twosend(session: CommandSession):
    await session.send('2*2*2\n'+two())


@on_command('four',aliases=('4','444','4*4*4'),only_to_me=False)
async def foutsend(session: CommandSession):
    await session.send('4*4*4\n'+four())


@on_command('five',aliases=('5','555','5*5*5'),only_to_me=False)
async def fivesend(session: CommandSession):
    await session.send('5*5*5\n'+five())


@on_command('six',aliases=('6','666','6*6*6')only_to_me=False)
async def sixsend(session:CommandSession):
    await session.send('6*6*6\n'+six())


@on_command('seven',aliases=('7','777','7*7*7'),only_to_me=False)
async def sevensend(session:CommandSession):
    await session.send('7*7*7\n'+seven())


@on_command('skewb',aliases=('sk','skewb'),only_to_me=False)
async def skewbsend(session:CommandSession):
    await session.send('skewb\n'skewb())


@on_command('leaves',aliases=('fy','fengye'),only_to_me=False)
async def leavessend(session:CommandSession):
    await session.send('leaves\n'+leaves())


@on_commend('clock',aliases=('cl','clock'),only_to_me=False)
async def clocksend(session:CommandSession):
    await session.send('clock\n'+clock)


@on_command('minx',aliases=('mx','minx',only_to_me=False))
async def minxsend(session:CommandSession):
    await session.send('minx\n'+minx)
```
#### 关于开源协议
禁止对代码进行商用，如果发现以法律解决

#### 图片（Pychram无法加载nonebot模块请忽略）
<img src="https://i.loli.net/2020/04/26/soiLEcJrnuIVTZN.jpg" width="40%"/>
- 注：因网络问题，暂时无法上传
