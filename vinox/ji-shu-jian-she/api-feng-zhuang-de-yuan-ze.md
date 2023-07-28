# API封装的原则

* 单一功能单独封装。
* 参数类型严格。
* 逻辑内部处理。
* 版本判断内部处理。

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
