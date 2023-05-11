# 技术选型：React & Mobx

React本身存在的问题：

1. 提供的api过于基础，许多常用功能留待用户自己封装解决。
2. 用useState声明状态太松散、太冗长。
3. 缺少computed这种非常实用的功能。
4. 不存在依赖追踪机制，需要手动使用React.memo等api做性能优化，繁琐、难度大且易产生bug。
5. 状态和方法需要零散地通过props层层传递给子组件，难以维护。当项目特别复杂时尤甚。
6. 对 setInterval window.addEventListener 这种功能支持度不好，需要小心避免踩坑。

使用mobx的理由：

1. 完整的computed功能。
2. 完整的依赖追踪机制，以组件为单位重新渲染，基本不需要再手动进行性能优化。
3. 完整的store功能，避免层层传递props。

Advantages of mobx:

* Automatic dependency tracking.
* True \`computed\` functionality.
* Better performance?

## useCallback

{% embed url="https://blog.csdn.net/Kobe_G/article/details/121752526" %}

useCallback是一个无奈的设计。

Mobx相当于用一种统一的、容易理解的方式解决了这些问题。

react唯一超过vue的优点是它对ts的支持比较好，vue的模板对ts支持太差了，目前还没有解决方案。尤雨溪自己也承认了这一点。

无论从写法还是性能上，react都没有“非用不可”的优势。

vue也吸收了react框架中好的部分，比如虚拟dom、jsx等等。
