<p align="center">
  <h2 align="center">Netease Recent Actions</h2>
  <p align="center">🎧 通过GitHub Action将你的网易云音乐的听歌记录生成svg</p>
</p>

## ⚙ 前置工作

获取网易云音乐用户 ID (https://music.163.com)

- 您的个人主页页面（`https://music.163.com/#/user/home?id=xxx`），`id` 为紧跟的那串数字

![user_id](https://user-images.githubusercontent.com/44596995/200237164-bf3b1c62-b2ee-4569-b5bf-bda06b09db08.png)

## 🔨 使用

需使用Github Actions，参考这个[仓库](https://github.com/zonemeen/zonemeen)的这个[文件](https://github.com/zonemeen/zonemeen/blob/a8c4549f38fd0ba254e3650eb0832a9e3cd1eb58/.github/workflows/job-work.yml)的配置，触发更新会自动提交`163.svg`这个文件至您的目标仓库

### 默认配置

![163-default](https://user-images.githubusercontent.com/44596995/200461439-01e74061-74a8-47af-8b43-87f83e247010.svg)

```yml
name: Netease Recent Actions

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '00 22 * * 0'

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: zonemeen/netease-recent-actions@v1.0.23 # 使用最新版本，最新版本查看https://github.com/marketplace/actions/netease-recent-actions
        with:
          id: '126764012' # 你的网易云音乐账号id
```

### 听歌排行类型

![163-type](https://user-images.githubusercontent.com/44596995/200461612-166fc262-4bf3-46f6-b0dc-e8d0cb5394ff.svg)

```yml
name: Netease Recent Actions

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '00 22 * * 0'

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: zonemeen/netease-recent-actions@v1.0.23
        with:
          id: '126764012'
          type: '0'
```

配置说明：`0`：为所有时间的听歌排行；`1`：默认为1，即近一周的听歌排行

### 歌曲数量

![163-number](https://user-images.githubusercontent.com/44596995/200461744-0d241454-7230-4fdd-846d-d97adfa573ff.svg)


```yml
name: Netease Recent Actions

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '00 22 * * 0'

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: zonemeen/netease-recent-actions@v1.0.23
        with:
          id: '126764012'
          number: 3
```

配置说明：歌曲数量自定义为`3`条，默认为`5`条

### 标题

![163-title](https://user-images.githubusercontent.com/44596995/200462389-820b61ac-7625-4c70-810a-563c7a7353b7.svg)

```yml
name: Netease Recent Actions

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '00 22 * * 0'

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: zonemeen/netease-recent-actions@v1.0.23
        with:
          id: '126764012'
          title: '最近在听'
```

配置说明：标题自定义为`最近在听`，默认为`Recently Played`

### 图片尺寸

![163-size](https://user-images.githubusercontent.com/44596995/200756757-62c04d9e-af87-47fa-96af-02ded58180c9.svg)

```yml
name: Netease Recent Actions

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '00 22 * * 0'

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: zonemeen/netease-recent-actions@v1.0.23
        with:
          id: '126764012'
          size: 60
```

配置说明：图片尺寸自定义为`60`，默认为`800`；尺寸越小，优点是svg尺寸较小，缺点是图片会失真变模糊

## 📄 开源协议

本项目使用 [MIT](./LICENSE) 协议






