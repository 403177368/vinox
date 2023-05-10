# /commonStore /rootStore

```typescript
// 全局store中保存环境变量、用户信息等数据。
interface CommonStore {
  env: {
    isAndroid: boolean;
    isIOS: boolean;
    isInWechat: boolean;
  };
  networkType: '';
  isDeviceOnline: boolean;
  deviceGeolocation: {};
  // http://nodejs.cn/api/os/os_userinfo_options.html
  userInfo: {};
  isUserLoggedIn: boolean;
  language: 'zh' | 'en';
}
```

