---
name: nestjs-conventions
description: Use when working in a NestJS project to keep project structure, layering, testing, validation, and error handling consistent across the codebase.
---

# NestJS Conventions

## Overview

NestJS code must follow consistent structural, layering, testing, validation, and error-handling conventions so any developer (or agent) can navigate and extend it without surprises.

## When to Use

- Creating or modifying NestJS modules, controllers, services, DTOs, or entities
- Writing unit or e2e tests
- Adding validation or exception handling
- Reviewing NestJS code

## Project Structure

Feature-based modular layout:

```
src/
  app.module.ts
  config/              # ConfigModule setup
  common/              # shared guards, filters, interceptors, pipes
    filters/           # global exception filter
    guards/
    pipes/
  modules/
    <feature>/
      <feature>.module.ts
      <feature>.controller.ts
      <feature>.service.ts
      dto/             # DTOs (class-validator)
      entities/        # TypeORM/Prisma entities or schemas
      <feature>.spec.ts
      <feature>.e2e-spec.ts
```

- One feature = one module directory.
- Keep DTOs/entities local to the feature; share only via `common/`.

## Layering & Dependency Injection

```
Controller → Service → Repository/data access
```

- **Controllers**: parse input, call service, return response. No business logic.
- **Services**: hold business logic and orchestration. No HTTP concerns.
- **Data access**: only persistence.
- Prefer `@Injectable()` and explicit constructor injection.
- Depend on interfaces/abstract classes over concrete implementations where it aids testing.
- Do NOT put business logic in controllers or DTOs.

## Validation

- Use `class-validator` decorators on DTOs.
- Enable `ValidationPipe` globally with `{ whitelist: true, forbidNonWhitelisted: true, transform: true }`.
- Validate at the boundary (DTO), not inside services.

## Error Handling

- Use a global exception filter to centralize error responses.
- Throw domain-appropriate exceptions (`NotFoundException`, `BadRequestException`, etc.).
- Do not leak stack traces or internal details to clients in production.

## Testing

- **Unit tests**: Jest, named `*.spec.ts`; mock dependencies; test each service/controller in isolation.
- **e2e tests**: Jest + Supertest, named `*.e2e-spec.ts`; run against a test database.
- Test both happy paths and error cases.

## Common Mistakes

- Business logic leaking into controllers or DTOs
- Missing global `ValidationPipe`, so invalid input reaches services
- Inconsistent DTO/entity placement
- Testing only the happy path
- Hardcoding config instead of using `ConfigModule`
