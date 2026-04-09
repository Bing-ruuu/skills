# skills
🚀 一键将文本、代码、PDF 文件转换为标准 Markdown 格式，高效生成规范的 .md 文档。

## ✨ 功能特性
- ✅ 支持纯文本、代码片段直接粘贴转换
- ✅ 支持本地文件（.txt/.py/.java 等代码文件）指定路径转换
- ✅ 支持 PDF 文件解析并转换为结构化 Markdown
- ✅ 自动格式化代码块、标题、列表等 Markdown 语法
- ✅ 输出标准 .md 文件，兼容 GitHub、Notion 等所有平台

## 🚀 快速开始
### 1. 环境要求
- Python 3.8+
- 依赖包：`pip install -r requirements.txt`

### 2. 基础使用
#### 方式一：直接粘贴内容转换
```bash
# 运行脚本，粘贴需要转换的内容
python skills.py --input "你的文本/代码内容" --output result.md
