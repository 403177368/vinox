# Error Handling

Rules about error handling:

* Only catch errors when they must be caught.
* Do not omit error message.

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
  // These code will run even if the login failed
  // We don't want to see such things happen
  doSomethingAfterLogin();
}
```

```typescript
// This is how error is handled in Golang.
// Things will get messy in JavaScript.
const [error, res] = await doSomething();
if (error) {
  // ...
}
```

Good example:

```typescript
async function a() {
  await login().catch(e => {
    message.error(e.message);
    throw new Error(e.message);
  });
  
  doSomethingAfterLogin();
}
```
