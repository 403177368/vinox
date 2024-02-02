# API封装的原则

* 单一功能单独封装。
* 参数类型严格。
* 逻辑内部处理。
* 版本判断内部处理。

#### API Design Principles

**Single Responsibility**

Each function should have a single responsibility. Encapsulate functionalities separately to maintain a clear separation of concerns.

**Strong Typing**

Ensure that the function parameters have strict type definitions. This will help to catch errors at compile time and enhance code readability and maintainability.

**Internal Logic Handling**

All the internal logic should be handled within the function itself to avoid exposing implementation details and to provide a clean, understandable API surface.

**Version Management Inside Function**

Handle version compatibility checks inside the function to ensure that the API consumers don't have to deal with version logic in their codebases.

```typescript
// Not recommended
// This exposes version checks to the API consumer, which is bad practice
if (getAppVersion() >= '0.0.2') {
  openWebView(5, 'https://example.com');
}
```

Whereas encapsulating the version check within the function is the correct approach:

```typescript
// Recommended
export function openWebView(count: number, url: string) {
  // Version check is done inside the function, abstracting complexity from the user
  if (getAppVersion() >= '0.0.2') {
    // Open the web view with provided count and URL
    window.location.href = resolveURL(
      `scheme://webview`, 
      {
        url: encodeURIComponent(url),
        count: `${count}`,
      },
    );
  } else {
    // Handle older version scenarios or inform the user
    console.error('Unsupported app version for openWebView');
  }
}
```

```typescript
// Good
export function openWebView({
  count: number;
  url: string;
}) {
  if (getAppVersion() >= '0.0.2') {
    window.location.href = resolveURL(
      `scheme://webview`,
      {
        url: encodeURIComponent(url),
        count: `${count}`,
      },
    );
  }
}
```

