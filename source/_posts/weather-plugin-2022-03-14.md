---
title: 配置天气预报
katex: false
mathjax: false
cover: false
categories: []
date: 2022-03-14 19:33:49
updated: 2022-03-14 19:33:49
tags:
---
## 配置文件

配置文件包含`weather`选项，可网站导航栏(navbar)显示天气预报插件。其基本配置如下：

```yml
weather:
  enable: true # 是否显示天气插件
  plugin: qweather # weather / qweather
  weather: # https://cj.weather.com.cn/plugin/simple
    # 只需粘贴WIDGET部分
    widget:
  qweather: # https://widget.qweather.com/create-simple/
    # 只需粘贴WIDGET部分
    widget:
```

`plugin`可选值`weather`或`qweather`。

* `weather`为[中国天气插件平台的网页简约插件](<https://cj.weather.com.cn/plugin/simple>)，该平台目前暂不可用。
* `qweather`为[和风天气开发平台简约版天气插件](https://widget.qweather.com/create-simple/)

## weather-中国天气

因中国天气插件平台无法使用，使用该选项将报错。

## qweather-和风天气

1. 登录
    登录/注册和[风天气开发平台](<https://id.qweather.com/#/login>)，并绑定邮箱和手机号。

2. 创建插件
    打开<https://widget.qweather.com/create-simple/>，设置插件名称和所需样式

3. 生成代码
    点击`生成代码`，将在下方生成一段`html`代码，如下所示：

    ```html
    <div id="he-plugin-simple"></div>

    <script>
        WIDGET = {
        "CONFIG": {
            "modules": "01234",
            "background": "1",
            "tmpColor": "FFFFFF",
            "tmpSize": "16",
            "cityColor": "FFFFFF",
            "citySize": "16",
            "aqiColor": "FFFFFF",
            "aqiSize": "16",
            "weatherIconSize": "24",
            "alertIconSize": "18",
            "padding": "10px 10px 10px 10px",
            "shadow": "1",
            "language": "auto",
            "borderRadius": "30",
            "fixed": "false",
            "vertical": "center",
            "horizontal": "left",
            "key": "3dd3fa00d5c14d7e962478a6e6bad3b3"
        }
    }
    </script>
    <script src="https://widget.qweather.net/simple/static/js/he-simple-common.js?v=2.0"></script>
    ```

4. 复制WIDGET
    复制其中的WIDGET部分，并在配置文件中进行设置。最终配置文件的`weather`部分如下所示（注意缩进）：

    ```yml
    weather:
        enable: true # 是否显示天气插件
        plugin: qweather # weather / qweather
        weather: # <https://cj.weather.com.cn/plugin/simple>
            # 只需粘贴WIDGET部分
            widget:
        qweather: # <https://widget.qweather.com/create-simple/>
            # 只需粘贴WIDGET部分
            widget: >
                WIDGET = {
                    "CONFIG": {
                        "modules": "01234",
                        "background": "1",
                        "tmpColor": "FFFFFF",
                        "tmpSize": "16",
                        "cityColor": "FFFFFF",
                        "citySize": "16",
                        "aqiColor": "FFFFFF",
                        "aqiSize": "16",
                        "weatherIconSize": "24",
                        "alertIconSize": "18",
                        "padding": "10px 10px 10px 10px",
                        "shadow": "1",
                        "language": "auto",
                        "borderRadius": "30",
                        "fixed": "false",
                        "vertical": "center",
                        "horizontal": "left",
                        "key": "3dd3fa00d5c14d7e962478a6e6bad3b3"
                    }
                }
    ```
