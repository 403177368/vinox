# Error Handling

Rules about error handling:

Bad examples:

```typescript
// The error is omitted silently, thus you will never know the reason of the error
try {
  doSomething();
} catch (e) {
  console.log('操作失败');
}
```

```typescript
async funciton a() { 
  await login().catch(e => {
    console.log('登录失败');
  });
  // These code will run even if the login is failed
  // We don't want to see such things happen
  doSomethingAfterLogin();
}
```
