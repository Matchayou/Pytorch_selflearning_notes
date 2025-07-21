---
date: 2025-07-20
tags:
  - transforms
  - 代码
  - pytorch
---
### 补充知识
API（**Application Programming Interface**）即**应用程序编程接口**，它是软件系统不同组件之间进行交互的接口。简单来说，API 是一组定义了不同程序模块如何相互通信和交互的规则和约定。API 提供了一种访问系统功能或数据的方法，而无需了解实现的内部细节。
#### **例子：使用天气API获取天气信息**
假设你正在开发一个天气应用，你想要获取某个城市的天气信息，并显示给用户。为了实现这个功能，你不需要自己去抓取天气数据或构建复杂的天气模型。相反，你可以使用 **一个已经存在的天气 API**，它提供了这个城市的天气数据。
### **步骤**：
1. **找到一个天气API**：  
    例如，`OpenWeatherMap` 是一个提供天气信息的公共 API。你只需要注册并获得一个 API 密钥（API Key），这个密钥是你调用 API 时用来验证身份的。
2. **向天气API发送请求**：  
    你可以通过发送一个 **HTTP 请求**（通常是 GET 请求）来获取某个城市的天气数据。请求的 URL 看起来可能像这样：
    `https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY`
    - `q=London` 表示你要查询伦敦的天气
    - `appid=YOUR_API_KEY` 是你从 OpenWeatherMap 获得的 API 密钥。
3. **API返回数据**：  
    当你发送请求时，API 会返回一个包含天气信息的 JSON 数据，
4. **使用返回的数据**：  
    你可以在应用中提取返回的天气信息，比如提取温度（`temp`）、湿度（`humidity`）以及天气描述（`description`）来显示给用户。
但以上所说api与tensor中的不相同，这里的 `_log_api_usage_once(self)` 可能会在内部记录下该 `Tensor` 类的实例化次数和时间，帮助开发者分析 Tensor 是否被过度使用，或者某些问题是否因为过多实例化导致的性能瓶颈等。这个 `API` 不是外部的网络接口，而是一个 **内部的日志记录机制**，帮助开发者追踪类实例的创建、调试系统、分析性能等。

## transforms结构及用法
transforms=工具箱
totensor resize = 工具

特定格式的图片→工具→想要的结果

## 代码笔记
![[transform_use_notes.ipynb]]
