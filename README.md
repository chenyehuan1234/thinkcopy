# ThinkCopy

一个桌面端剪贴板事实核查工具——复制任意文本，AI 自动帮你核实内容是否准确。

## 功能

- **自动监测剪贴板**：复制文本后自动触发评估，无需手动操作
- **AI 事实核查**：通过 DeepSeek API 对剪贴板内容进行联网事实核查，指出正确与错误之处
- **Markdown 渲染**：评估结果以 Markdown 格式在右侧悬浮窗口中美观展示，支持标题、粗体、斜体、行内代码等样式
- **简洁轻量**：基于 Python tkinter 构建，无需额外 GUI 框架依赖

## 截图

> 将截图放在 `screenshots/` 目录下，在此处引用。

## 环境要求

- Python 3.8+
- Windows / macOS / Linux

依赖均为 Python 标准库，无需额外安装。

## 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/你的用户名/thinkcopy.git
cd thinkcopy
```

### 2. 配置 API Key

编辑 `clipboard_overlay.py` 第 9 行，填入你的 DeepSeek API Key：

```python
API_KEY = "你的 DeepSeek API Key"
```

> 获取 API Key：前往 [DeepSeek 开放平台](https://platform.deepseek.com/) 注册并创建 API Key。

### 3. 运行

```bash
python clipboard_overlay.py
```

复制任意文本，右侧窗口将自动弹出 AI 评估结果。

## 工作原理

1. 定时检测系统剪贴板内容（Windows 使用 PowerShell，macOS/Linux 使用 tkinter）
2. 发现新内容后，发送至 DeepSeek API，使用 `deepseek-v4-flash` 模型进行联网搜索事实核查
3. 返回的 Markdown 结果在右侧悬浮窗口中渲染展示

## 项目结构

```
thinkcopy/
├── clipboard_overlay.py   # 主程序
├── .gitattributes         # Git 换行符配置
└── README.md              # 项目说明
```

## 许可证

MIT License
