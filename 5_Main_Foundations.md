# 地基一：OpenAI 协议层的“原始请求”理解

## 本质：Agent 的核心是循环（Loop）。即：User Prompt → API（带tools） → 解析tool_calls→ 执行本地函数 → 将结果以tool角色回传 → API 二次推理 → 输出最终答案。

<img width="2530" height="1338" alt="mermaid-diagram-1787998463020" src="https://github.com/user-attachments/assets/920c8cc6-dc70-4994-90b6-e524f01f591e" />

### Demo:原生curl
<img width="1138" height="702" alt="image" src="https://github.com/user-attachments/assets/7b93449c-df90-42df-9b79-4975d0c933c4" />

### Agent底层工作原理

<img width="1616" height="922" alt="image" src="https://github.com/user-attachments/assets/ae7e74c6-21b7-4d61-84dc-91cf82ab9494" />

# 地基二: 安全沙箱（命令解析器）

## 本质：安全沙箱不是“过滤危险字符”，而是“拒绝执行任意命令，仅将 AI 的输出映射到预设的绝对路径命令上”

**粉碎直觉（为什么正则过滤无效）**
- 绕过太简单
- 利用编码绕过、换行符绕过
- 只允许 AI 从预定义列表中选择命令和参数，由 Python 代码负责拼接和执行

## 三层防御架构

<img width="1551" height="3105" alt="deepseek_mermaid_20260830_0804e3" src="https://github.com/user-attachments/assets/bc73533f-a037-4ba8-ae5d-a4e016708bcc" />
