# 地基一：OpenAI 协议层的“原始请求”理解

## 本质：Agent 的核心是循环（Loop）。即：User Prompt → API（带tools） → 解析tool_calls→ 执行本地函数 → 将结果以tool角色回传 → API 二次推理 → 输出最终答案。

<img width="2530" height="1338" alt="mermaid-diagram-1787998463020" src="https://github.com/user-attachments/assets/920c8cc6-dc70-4994-90b6-e524f01f591e" />

### Demo:原生curl
<img width="1138" height="702" alt="image" src="https://github.com/user-attachments/assets/7b93449c-df90-42df-9b79-4975d0c933c4" />

### Agent底层工作原理

<img width="1616" height="922" alt="image" src="https://github.com/user-attachments/assets/ae7e74c6-21b7-4d61-84dc-91cf82ab9494" />
