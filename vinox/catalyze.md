# Catalyze

Catalyze is a lib aiming at providing general-purpose architecture for frontend projects.

First of all, a /src/common/config.ts file is needed to define most common types for your project. These types will go through your whole project, serving as cornerstones for all the other upper structures.

```typescript
// src/common/config.ts
export type Config = DefineAppConfig<{
  EnvId: '';
  Env: {};
}>;
```

No matter what frontend framework your project is based upon, features like environment variables, navigating, internationalization, theme and so on are inevitable.

It is recommended to use NextJS as your frontend framework because it provides SSR and routing system out of box and can be easily integrated with backend libs like express.

## Catalyze

### Navigating



## Catalyze-admin
