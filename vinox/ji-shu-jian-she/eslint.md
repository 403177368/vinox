# Eslint

```bash
npm install eslint-config-airbnb --save-dev
npm install eslint-config-airbnb-typescript --save-dev
npm install eslint-config-vue --save-dev
```

{% embed url="https://www.npmjs.com/package/eslint-plugin-vue" %}

```typescript
// .eslintrc.js
module.exports = {
  extends: [
    'plugin:vue/recommended',
    'airbnb',
    'airbnb-typescript',
  ],
};
```

## Deprecated

{% embed url="https://www.npmjs.com/package/@vue/eslint-config-airbnb" %}
