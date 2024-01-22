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

## Before We Start

It is recommended to use NextJS as your frontend framework because it provides SSR and routing system out of box and can be easily integrated with backend libs like express. NextJS is designed for SSR but it is feasible to disable SSR for specified pages or routes, so there is no need to worry about performance drawbacks. Also, NextJS can be used solely as a build tool to generate static sites.

To lower the burden of development, it is recommended to use one service to serve web pages under multiple web domains.

## Catalyze

### Navigating



## Catalyze-admin

### Permission

No admin system can bypass permissions. Permissions are organized in a tree structure.

***
