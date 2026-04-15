# Backend Code Style (Spring Boot)

## 1. 架构分层（红线原则）
- **Controller 层**：仅负责路由分发、参数接收与校验（使用 JSR-303 注解）、返回统一的 Result 包装对象。**绝对禁止在 Controller 中编写业务逻辑判断。**
- **Service 层**：承载所有核心业务逻辑、状态流转和事务控制（`@Transactional`）。复杂的算法或判断必须有清晰的注释。
- **Repository 层**：纯粹的数据访问，不做业务计算。

## 2. API 与参数规范
- **RESTful 风格**：接口路径使用名词复数，通过 HTTP Method 区分动作。禁止使用动词作为路径（错误示例：`/api/createUser`，正确示例：`POST /api/users`）。
- **对象传递**：入参使用 `DTO` (Data Transfer Object)，出参使用 `VO` (View Object)，实体类 `Entity` 严禁直接暴露给 Controller 层返回。

## 3. 健壮性与可维护性
- **零魔法值**：代码中严禁出现不明含义的数字或字符串。必须提取为 `public static final` 常量或使用 `Enum` 枚举类。
- **异常处理**：禁止随意吞掉异常（`catch` 后不做处理）。必须抛出自定义业务异常（如 `BusinessException`），由全局异常处理器（GlobalExceptionHandler）统一捕获并返回标准化错误码。

## 4. 日志规范
- 关键业务节点的执行、外部系统集成调用前后，必须使用 `log.info` 记录核心参数。
- 捕获到的非预期异常必须使用 `log.error("错误描述", e)` 打印完整堆栈。