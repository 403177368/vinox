# computed的使用

> _Make sure that everything that can be derived from the application state, will be derived. Automatically._
>
> [_https://mobx.js.org/getting-started_](https://mobx.js.org/getting-started)

#### Leveraging Computed Values in MobX

When using MobX to manage your application state, it's highly efficient to take advantage of computed values. These are values that are automatically derived from your state whenever it changes, ensuring that your app reacts appropriately to state alterations.

**Basic Example of a Computed Value**

```javascript
import { observable, computed } from 'mobx';

class TodoList {
  @observable todos = [];

  @computed get unfinishedTodoCount() {
    return this.todos.filter(todo => !todo.finished).length;
  }
}
```

**Using Computed Values in React Components**

```javascript
import React from 'react';
import { observer } from 'mobx-react';

const TodoListView = observer(({ todoList }) => (
  <div>
    <ul>
      {todoList.todos.map(todo => (
        <li key={todo.id}>{todo.title}</li>
      ))}
    </ul>
    Tasks left: {todoList.unfinishedTodoCount}
  </div>
));
```

**Smart Performance with Computed Values**

Computed values only re-calculate when one of the values they depend on changes, which is highly performance-optimized.

```javascript
class Store {
  @observable price = 0;
  @observable amount = 1;

  @computed get total() {
    return this.price * this.amount;
  }
}
```

Remember, computed values are great for keeping your UI in sync with the state while being as performant as possible. Check out MobX's documentation at https://mobx.js.org/getting-started for more on computed values.

**Avoiding State Duplication with MobX**

One of MobX's core principles is to keep your application state as the single source of truth. Avoid state duplication by leveraging computed values to create reactive derivations of your state. This ensures consistency and prevents the complexity that can come with maintaining multiple sources of state information.

**Single Source of Truth**

```javascript
import { observable, computed } from 'mobx';

class UserProfile {
  @observable firstName = 'John';
  @observable lastName = 'Doe';

  @computed get fullName() {
    return `${this.firstName} ${this.lastName}`;
  }
}
```

In this example, `fullName` is a computed property that automatically updates when `firstName` or `lastName` changes. This way, you never have to manually synchronize the `fullName` when the underlying state changes.

**Reactive Updates with Computed Values**

Remember to use computed values rather than duplicating state that can be derived. MobX will take care of the necessary updates for you, which helps in preventing inconsistencies and unnecessary re-renders in your applications.

Always refer to the observable state when you need to derive data. This will help you maintain a single source of truth and improve the maintainability of your application.
