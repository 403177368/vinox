# Error Handling

Rules about error handling:

Bad examples:

```typescript
// You will never know the reason of the error
try {
  doSomething();
} catch (e) {
  console.log('操作失败');
}
```
