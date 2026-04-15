# name
write-test

# goal
为指定的类或组件编写单元测试

# steps
1. 使用 serena 分析目标代码的公共方法和依赖
2. 在对应的测试目录下创建测试文件（如 `*.spec.ts` 或 `*Test.java`）
3. 编写正常路径（Happy Path）和异常路径（Edge Cases）测试
4. 使用 filesystem 写入测试代码

# constraints
- 只测试业务逻辑，不测试框架本身的 API
- 必须 Mock 外部依赖（如数据库调用、HTTP 请求）
- 不修改源代码本身