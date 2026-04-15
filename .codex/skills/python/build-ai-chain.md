# name
build-ai-chain

# goal
基于 LangChain / LangGraph 开发大模型交互链路、Agent 或 RAG 检索模块

# steps
1. 使用 serena 分析现有的 AI 平台架构（如模型网关、向量库连接）
2. 定义清晰的 Prompt Template，并将变量结构化
3. 构建具体的处理节点 (Node) 或检索链 (Chain)，如集成 Milvus 进行向量检索
4. 组装图或链路流转逻辑，并处理可能出现的模型幻觉或调用超时
5. 使用 filesystem 写入代码

# constraints
- **高度模块化**：Intent 路由、Prompt 构建、模型调用、输出解析必须拆分为独立的函数或类
- 调用大语言模型时，必须设置合理的超时时间和重试机制
- 在与 Milvus 等向量数据库交互时，必须处理好索引建立和相似度阈值匹配的异常边界