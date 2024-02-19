# Domain Model

{% embed url="https://docs.github.com/en/graphql/reference/objects" %}

{% embed url="https://www.thoughtworks.com/en-sg/insights/blog/agile-project-management/domain-modeling-what-you-need-to-know-before-coding" %}

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
