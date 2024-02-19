# Domain Objects

{% embed url="https://docs.github.com/en/graphql/reference/objects" %}

* [https://www.codewithjason.com/difference-domains-domain-models-object-models-domain-objects/](https://www.codewithjason.com/difference-domains-domain-models-object-models-domain-objects/)
* [https://java-design-patterns.com/patterns/domain-model/](https://java-design-patterns.com/patterns/domain-model/)

```typescript
interface User {
  id: string;
  name: string;
  following: FollowingConnection;
  createdAt: number;
}
```
