# GOMOKU BRAIN COMPETITION

[![Build Status](https://travis-ci.org/SSTIA/fun-portal.svg?branch=master)](https://travis-ci.org/SSTIA/fun-portal)
[![experimental](http://badges.github.io/stability-badges/dist/experimental.svg)](http://github.com/badges/stability-badges)
[![GPL Licence](https://badges.frapsoft.com/os/gpl/gpl.svg?v=103)](https://opensource.org/licenses/GPL-3.0/)
[![David](https://david-dm.org/SSTIA/fun-portal.svg)](https://david-dm.org/SSTIA/fun-portal)

## Introduction

> Gomoku is an abstract strategy board game. Also called Gobang or Five in a Row, it is traditionally played with Go pieces (black and white stones) on a go board with 19x19 (15x15) intersections; however, because pieces are not moved or removed from the board, gomoku may also be played as a paper and pencil game. This game is known in several countries under different names.

More information about Gomoku, see [Gomoku - Wikipedia](https://en.wikipedia.org/wiki/Gomoku)

In our game, two players take turns as black to move first. There are six rounds in total and each player moves first for three times.

## Online Judge System

Visit [GomokuJudge](http://202.121.178.229/) to take part in our competition!

Login in via your JAccount and submit your code altered from the file **main.c** we provided.

The max size of Source code and Compiled exe are both 1MB.

There are some warnings:
1. Do not copy others' source code. All the code you submitted will be checked for plagiarism. Copycats will fail this project!
2. Do not share your source code with others. Similar submissions will be treated as plagiarism.
3. Do not use alternative account to submit your code, otherwise you will be recognized as a copycat.
4. Do not abuse our cloud execution service, such as intentionally trying to shutdown our judge machine.

## Deployment

(WIP)

Dependencies:

* Node.js
* MongoDB
* Redis
* rabbitMQ

Install dependencies on Debien/Ubuntu
```
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
$ nvm install 9 && nvm use 9
$ sudo apt-get install mongodb redis-server rabbitmq-server
```

If you are in Mainland China, it's recommended to use registry by `taobao` (or use `cnpm`)

```
$ npm config set registry https://registry.npm.taobao.org
```

Run the following command to create configuration scripts for both debug and in-production deployments:

```
$ touch config.debug.yaml
$ touch config.production.yaml
```

Edit the configuration according to the comments given. Then, excecute the following command to build the package:

```
$ npm install -g npminstall
$ npminstall
$ run build:server
$ run build:ui
```


Finally, run

```
$ npm run start
```

to start the server.

## Matching



## Openings

**Important: This part is only for reference, you may not dismiss these when developing your own AI.**

Black (the player who makes the first move) was long known to have a big advantage, so we will specify the beginning of the game so that both players will get the same advantage to make the game fair.

We assume the openings are exactly the displayed 5x5 square in the center, x represents black and o represents white

The followings are all of the opening situations (on the Judge System):

### 直指 (黑优)

#### 1. 花月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o | x |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 2. 雨月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x | x |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 3. 松月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   | x |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 4. 溪月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   | x |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 5. 寒星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   | x |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 6. 瑞星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   | x |   |   |
  +---+---+---+---+---+
```
#### 7. 金星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   | x |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```

### 斜指 (黑优)

#### 8. 浦月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   | x |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 9. 云月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x | x |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 10. 峡月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o | x |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 11. 银月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   | x |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 12. 岚月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   | x |   |
  +---+---+---+---+---+
```
#### 13. 名月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   | x |   |   |   |
  +---+---+---+---+---+
```
#### 14. 水月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   | x |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 15. 恒星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   | x |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 16. 明星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   | x |   |   |
  +---+---+---+---+---+
```

### 直指 (白优或均势)
#### 17. 残月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   | x |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 18. 新月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   | x |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 19. 丘月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   | x |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 20. 山月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   | x |   |
  +---+---+---+---+---+
```
#### 21. 游星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   | x |
  +---+---+---+---+---+
```
#### 22. 疏星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   | x |
  +---+---+---+---+---+
6 |   |   | o |   |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```

### 斜指 (白优或均势)
#### 23. 斜月
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   | x |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 24. 长星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   | x |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   |   |
  +---+---+---+---+---+
```
#### 25. 流星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 |   |   |   |   | x |
  +---+---+---+---+---+
```
#### 26. 彗星
```
    5   6   7   8   9
  +---+---+---+---+---+
5 |   |   |   |   |   |
  +---+---+---+---+---+
6 |   |   |   | o |   |
  +---+---+---+---+---+
7 |   |   | x |   |   |
  +---+---+---+---+---+
8 |   |   |   |   |   |
  +---+---+---+---+---+
9 | x |   |   |   |   |
  +---+---+---+---+---+
```


## Reference
1. [Gomoku - Wikipedia](https://en.wikipedia.org/wiki/Gomoku)
2. [五子棋26种开局 - 百度文库](http://wenku.baidu.com/link?url=oDoH2qYWR6MRDVLuwNRnYDlOUN8n0Zg5YuVg5IyFR58v8nI1A0wDMC2ERctDs5Nwmg9cQIXnI33cM7EG_rrafprMe0idLYzYO8hVnPCu_tG)

---
Online Judge System by [GomokuFun](https://github.com/sse2016-gomoku-fun/)

Server by Luke Lazurite, Liu Yihao and Shen zheyu

Manual written by Liu Yihao

JI-SSTIA All Right Reverved
