# MCP 使用规范

## filesystem
- 所有代码修改必须通过 filesystem
- 不允许直接生成整文件覆盖

---

## serena
- 修改前必须分析代码结构
- 必须确认类/函数位置

---

## context7
- 查询 API / 官方文档
- 禁止凭记忆编写接口

---

## github
- 仅用于提交代码，不自动创建 PR
- 每次提交必须使用 Conventional Commits 规范（如 `feat:`, `fix:`, `docs:`, `refactor:`）
- Commit message 必须清晰说明修改了哪个模块以及修改原因
- 提交前必须确保代码通过本地的语法检查（如果可用）

---

## 规则

- 不允许跳过 MCP 直接修改代码
- 不允许未分析直接修改