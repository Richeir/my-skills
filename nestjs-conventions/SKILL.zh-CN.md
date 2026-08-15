---
name: nestjs-conventions
description: 当在 NestJS 项目中工作时使用，以确保整个代码库的项目结构、分层、测试、校验和错误处理保持一致。
---

# NestJS 项目规范

## 概述

NestJS 代码必须遵循一致的结构、分层、测试、校验和错误处理约定，让任何开发者（或代理）都能无障碍地浏览和扩展它。

## 何时使用

- 创建或修改 NestJS 的模块、控制器、服务、DTO 或实体
- 编写单元测试或 e2e 测试
- 添加校验或异常处理
- 审查 NestJS 代码

## 项目结构

基于功能的模块化布局：

```
src/
  app.module.ts
  config/              # ConfigModule 配置
  common/              # 共享的守卫、过滤器、拦截器、管道
    filters/           # 全局异常过滤器
    guards/
    pipes/
  modules/
    <feature>/
      <feature>.module.ts
      <feature>.controller.ts
      <feature>.service.ts
      dto/             # DTO（class-validator）
      entities/        # TypeORM/Prisma 实体或 schema
      <feature>.spec.ts
      <feature>.e2e-spec.ts
```

- 一个功能 = 一个模块目录。
- DTO/实体放在功能目录内；只有需要跨模块共享时才放到 `common/`。

## 分层与依赖注入

```
Controller → Service → 数据访问层
```

- **控制器**：解析输入、调用服务、返回响应，不含业务逻辑。
- **服务**：承载业务逻辑与编排，不涉及 HTTP 细节。
- **数据访问**：只负责持久化。
- 优先使用 `@Injectable()` 和显式的构造函数注入。
- 有助于测试时，优先依赖接口/抽象类而非具体实现。
- 不要在控制器或 DTO 中写业务逻辑。

## 校验

- 在 DTO 上使用 `class-validator` 装饰器。
- 全局启用 `ValidationPipe`，配置 `{ whitelist: true, forbidNonWhitelisted: true, transform: true }`。
- 在边界处（DTO）校验，而不是在服务内部校验。

## 错误处理

- 用全局异常过滤器统一错误响应。
- 抛出语义合适的异常（`NotFoundException`、`BadRequestException` 等）。
- 生产环境不要向客户端泄露堆栈或内部细节。

## 测试

- **单元测试**：Jest，命名 `*.spec.ts`，mock 依赖，隔离测试每个服务/控制器。
- **e2e 测试**：Jest + Supertest，命名 `*.e2e-spec.ts`，针对测试数据库运行。
- 同时覆盖正常路径与错误路径。

## 常见错误

- 业务逻辑泄漏到控制器或 DTO
- 缺少全局 `ValidationPipe`，导致非法输入直达服务
- DTO/实体摆放不一致
- 只测正常路径
- 硬编码配置，而不是使用 `ConfigModule`
