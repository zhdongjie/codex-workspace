# name
create-fastapi-endpoint

# goal
创建一个基于 FastAPI 的异步后端接口

# steps
1. 使用 serena 分析现有的路由文件 (routers) 和依赖注入结构
2. 定义 Pydantic 模型作为请求入参 (Request) 和响应出参 (Response)
3. 在对应的 router 文件中添加 `@router.get/post` 路由方法
4. 确保核心业务逻辑使用 `async def` 和 `await` 进行异步处理
5. 使用 filesystem 写入代码

# constraints
- 必须基于 Python 3.13.1 的原生类型提示进行 Pydantic 字段定义
- 严格分离路由定义与复杂业务逻辑，保持 Controller 层轻量
- 必须包含标准的 HTTP 状态码处理和异常抛出 (HTTPException)