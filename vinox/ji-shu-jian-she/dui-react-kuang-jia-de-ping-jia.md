# 技术选型：React & Mobx

React本身存在的问题：

1. 提供的api过于基础，许多常用功能留待用户自己封装解决。
2. 用useState声明状态太松散、太冗长。
3. 缺少computed这种非常实用的功能。
4. 不存在依赖追踪机制，需要手动使用React.memo等api做性能优化，繁琐、难度大且易产生bug。
5. 状态和方法需要零散地通过props层层传递给子组件，难以维护。当项目特别复杂时尤甚。
6. 对 setInterval window.addEventListener 这种功能支持度不好，需要小心避免踩坑。

#### Disadvantages of React

React, while a popular front-end framework, does have its pain points:

* **Basic API Offering**: React's APIs are seen as too elemental, leaving developers to encapsulate and solve for common functionality on their own.
* **Verbose State Management**: The `useState` hook can result in verbose and loose code, particularly in complex components.
* **Lack of Computed Features**: React does not offer an out-of-the-box `computed` functionality that is as powerful as some other frameworks, which can streamline state management.
* **No Dependency Tracking**: Without built-in dependency tracking, developers often have to resort to manual optimizations like `React.memo`, which can be cumbersome and error-prone.
* **Prop Drilling**: State and methods sometimes need to be passed down multiple levels through props, which can quickly become hard to maintain in large applications.
* **Poor Support for Certain Browser APIs**: Using browser APIs such as `setInterval` and `window.addEventListener` can be tricky in React, requiring caution to avoid common pitfalls.
* **Server-Side Rendering Complexity**: Although possible, server-side rendering in React can be complex and may require additional configuration and handling.
* **API Stability**: React's API changes, like the version 13 upgrade, can be disruptive and may indicate less stability in long-term projects.
* **Documentation Quality**: The inconsistency in the quality of React's documentation can be a challenge for some developers.
* **Closure Traps with Hooks**: Misusing React's hooks, especially `useEffect`, can lead to closure-related bugs that are hard to diagnose and fix.

These challenges may steer developers towards alternatives like MobX or Vue, which attempt to address some of React's shortcomings. However, React continues to be widely used due to its strong community, regular updates, and integration with other tools and libraries in the JavaScript ecosystem.

<mark style="color:green;">使用mobx的理由：</mark>

1. <mark style="color:green;">完整的computed功能。</mark>
2. <mark style="color:green;">完整的依赖追踪机制，以组件为单位重新渲染，基本不需要再手动进行性能优化。</mark>
3. <mark style="color:green;">完整的store功能，避免层层传递props。</mark>

<mark style="color:green;">Advantages of mobx:</mark>

* <mark style="color:green;">Automatic dependency tracking.</mark>
* <mark style="color:green;">True \`computed\` functionality.</mark>
* <mark style="color:green;">Better performance?</mark>

<table data-full-width="true"><thead><tr><th width="299.3333333333333">Next.js</th><th width="324">Vite</th><th></th></tr></thead><tbody><tr><td><ul><li><mark style="color:green;">能进行服务端渲染，动态输出html，由此“前端”包含了后端服务的“前端”。</mark></li><li><mark style="color:green;">可在一个nextjs服务内开发多个project，减少仓库数目，降低维护成本。</mark></li></ul></td><td><ul><li><mark style="color:green;">配置简洁，vue官方维护的项目文档质量都不错。</mark></li></ul></td><td></td></tr><tr><td><ul><li><mark style="color:red;">API不太稳定，13版本断崖式升级，团队责任心成迷，issue处理不及时。</mark></li><li><mark style="color:red;">文档质量一般。</mark></li></ul></td><td><ul><li><mark style="color:red;">需要使用vite-legacy插件兼容不支持es-module的浏览器。</mark></li></ul></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

## useCallback

{% embed url="https://blog.csdn.net/Kobe_G/article/details/121752526" %}

useCallback是一个无奈的设计。

Mobx相当于用一种统一的、容易理解的方式解决了这些问题。

react唯一超过vue的优点是它对ts的支持比较好，vue的模板对ts支持太差了，目前还没有解决方案。尤雨溪自己也承认了这一点。

无论从写法还是性能上，react都没有“非用不可”的优势。

vue也吸收了react框架中好的部分，比如虚拟dom、jsx等等。

## 闭包陷阱

[https://betterprogramming.pub/understanding-the-closure-trap-of-react-hooks-6c560c408cde](https://betterprogramming.pub/understanding-the-closure-trap-of-react-hooks-6c560c408cde)

### 一些非常容易产生bug的写法

```typescript
const Header = observer(({
  count,
}: {
  count: number;
}) => {
  const [num, setNum] = useState<number>(0);

  const local = useLocalObservable(() => ({
    get countStr() {
      return `${count}`;
    },
    get totalCount() {
      return count + num;
    },
    onButtonClicked() {
     console.log(count);
    },
  }));

  useEffect(() => {
    setInterval(() => {
      console.log(num);
      setNum((v) => v + 1);
    }, 1000);
    window.addEventListener('resize', () => {
      console.log(num);
    });
  }, []);

  return <div onClick={() => setNum(num + 1)}>{num}</div>;
});
```

### 建议解决方案

{% embed url="https://mobx.js.org/react-optimizations.html" %}

```typescript
export default observer(({
  getCount,
}: {
  getCount(): number;
}) => {
  const local = useLocalObservable(() => ({
    get countStr() {
      return `${getCount()}`;
    },
    onButtonClicked() {
      console.log(getCount());
    },
    fn: _.debounce(() => {
      // ...
    }, 300),
  }));
  
  return <div onClick={local.onButtonClicked} />
});
```
