 to-md

将文本、代码或 PDF 转换为 Markdown 格式的 Claude Code Skill。
##需求：
1.claude code电子书转成markdown，写脚本或者用to-md skill+写脚本均可。
2.claude code skills，将claude code泄露的源码和泄露后的电子书蒸馏成skills，vibe coding喂给coding agent时AI直接可以通过claude code demo的模型开发出各种衍生agent。claude code to everything！

##design.md
大的复杂文件结构：
<img width="1733" height="985" alt="image" src="https://github.com/user-attachments/assets/0ae849d5-2d3a-490b-819c-8a275fd94388" />
~/.claude/skills/react-component-review/
  ├── SKILL.md                  # 核心指令 + 元数据（建议控制在 400 行内）
  │
  ├── templates/                # 常用模板（Claude 按需读取）
  │   ├── functional.tsx.md
  │   └── class-component.md
  │
  ├── examples/                 # 优秀/反例（给 Claude 看标准）
  │   ├── good.md
  │   └── anti-pattern.md
  │
  ├── references/               # 规范、规则、禁用词表
  │   ├── hooks-rules.md
  │   └── naming-convention.md
  │
  └── scripts/                  # 可执行脚本（需开启 code execution）
      ├── validate-props.py
      └── check-cycle-deps.sh


##task.md

TODO LIST

##更新日志
【每2到3天更一次吧】
## 功能特性

- **文本转 Markdown** - 直接粘贴文本内容，快速转换为 Markdown 格式
- **代码转 Markdown** - 支持 Python、JavaScript、TypeScript、JSON 等多种语言的代码片段
- **PDF 转 Markdown** - 将 PDF 文件转换为 Markdown，保留结构层级、表格格式
- **智能检测** - 自动识别内容类型和编程语言
- **格式保留** - 保持原始缩进、代码块格式

## 支持的文件类型

| 类型 | 扩展名 | 处理方式 |
|------|--------|----------|
| Python | `.py` | 代码块 (python) |
| JavaScript | `.js` | 代码块 (javascript) |
| TypeScript | `.ts` | 代码块 (typescript) |
| Markdown | `.md` | 直接写入 |
| JSON | `.json` | 代码块 (json) |
| 纯文本 | `.txt` | 直接写入 |
| PDF | `.pdf` | 提取文本+结构转换 |

## 使用方法

在 Claude Code 中使用 `/to-md` 命令：

### 转换文件

```bash
/to-md /path/to/file.py
/to-md C:\Users\test\document.pdf
```

### 转换内联内容

```
/to-md
def hello():
    print("world")
```

## 输出示例

**代码文件转换：**
```
[已转换] main.py → main.md
语言：python
保存至：C:\Users\test\main.md
```

**PDF 转换：**
```
[已转换] document.pdf → document.md
类型：PDF
页数：12
保存至：C:\Users\test\document.md
```

## 安装

将此 skill 添加到 Claude Code：

1. 将 `SKILL.md` 内容复制到你的 skills 目录
2. 或通过 Claude Code 的 skill 管理器导入

## PDF 转换细节

- 提取 PDF 中的文本内容
- 保留标题层级结构 (h1/h2/h3)
- 表格转换为 Markdown 表格格式
- 图片暂时用占位符标注
- 代码块保持原有缩进

## 注意事项

- PDF 为扫描件（无文本层）时无法提取内容
- 加密或损坏的 PDF 文件无法处理
- 文件大小超过 1MB 时建议分段处理


