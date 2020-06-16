# 一个基于 Rasa 的天气查询机器人[后端部分]

本项目是基于 Rasa 的天气查询机器人项目的后端部分，另一个部分是前端部分位于 [basic_weather_bot_client](https://github.com/howl-anderson/basic_weather_bot_client)

## 环境要求 ##
Mac OS X or Linux

Windows supporting is on the radar.

## 安装

### 安装依赖 ###
安装 python 等各种软件包依赖

```bash
make install
```

### 安装模型文件 ###
下载已经预先训练好的 MITIE 的模型文件

```bash
make download
```

## 训练

```bash
rasa train
```

## 启动

### Step 1: 启动 action server
```bash
SENIVERSE_KEY=xxxx rasa run actions
```

`xxxx` 部分应该替换成从 [心知天气](https://www.seniverse.com/) 申请获得的 API key 。用户可以免费注册，注册后可以在后台找到 `我的API密钥`。

### Step 2: 启动rasa server ###

```bash
make run_model
```

### [可选] 启动 rasa x
为了能够在不使用（或者没有）客户端的情况下以及测试模型的情况，我们可以使用 rasa x

```bash
rasa x --enable-api --auth-token 12345678
```

启动后会自动打开浏览器窗口
