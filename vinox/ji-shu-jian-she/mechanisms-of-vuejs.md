# Mechanisms of VueJS

```
Mechanisms of VueJS
  什么是dep？
  什么是getter/setter？
  什么是proxy getter/setter？什么是reactive getter/setter？
  一个vue组件有几种watcher？
  一个vue组件的第一次依赖收集是何时进行的？
  有computed: { checkedItemList() { ... } }，是否每次使用this.checkedItemList的时候都会evaluate这个函数呢？
  vue组件的创建顺序是什么样的呢？
  一个dep的值的变动会触发框架进行哪些操作呢？
```

#### What is `dep` in Vue?

In Vue.js, `dep` is short for dependency. It's a core concept used by Vue’s reactivity system to keep track of which components need to be re-rendered when state changes. A `dep` is essentially a list of "subscribers", or watchers, that should be notified when the state they depend on is mutated.

Whenever a reactive property is read, Vue collects dependencies by tracking which properties a component renders. It does this with getters and setters, and when a property changes, it triggers the setters. The setter then notifies each `dep` associated with that property.

Here's how that works in a simplified flow:

1. A component reads a reactive property.
2. Vue recognizes this and adds the component's watcher to the `dep` instance corresponding to the property.
3. When the reactive property changes, Vue calls the `dep`'s `notify()` method.
4. The `notify()` method invokes all the registered watchers, causing the component to re-render with the updated state.

#### How dep is Created in Vue.js

When Vue.js initializes a component, it recursively converts all of its `data` properties into getter/setters to make them reactive. This process is part of Vue's reactivity system initialization. Here is a step-by-step breakdown:

1. **Observer Instance:** Vue creates an observer instance for every data property in the component's `data` option. This observer walks through each property and converts them to getter/setters using `Object.defineProperty`.
2. **Dependency Instances:** For each reactive property, Vue initializes a `Dep` instance. This is where the magic happens. The `Dep` instance is an observable that can have multiple directives subscribing to it.
3.  **Getters and Setters:**

    * **Getter:** When a property is accessed, the getter is invoked. The getter function performs a dependency-tracking operation, where it adds the currently active component's watcher to the list of subscribers if it's not already subscribed.
    * **Setter:** When a property is modified, the setter is invoked. The setter will then trigger the `dep.notify()` method, which notifies all subscriber watchers that the state has changed.

    Through these steps, Vue sets up a reactive system where `dep` acts as a hub for dependencies (watchers) that should react to changes in the data properties.

