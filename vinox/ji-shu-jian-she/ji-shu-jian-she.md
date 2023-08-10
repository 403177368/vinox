# 技术建设

1. 安装fish-shell
2. 安装n。
3. 安装vscode stylelint等插件。
4.  理解rebase脚本和deploy脚本的原理。它们解决了什么问题？\
    <mark style="background-color:green;">如何合并多条commits？</mark>

    什么是base commit？

    <mark style="background-color:green;">为什么运行git pull命令遇到冲突，解决冲突之后，再运行git rebase命令，又遇到了一模一样的冲突？</mark>

    <mark style="background-color:green;">提交了太多条commit，之后进行rebase操作的时候遇到太多冲突，有没有办法规避？</mark>
5.  进程 线程 堆内存 栈内存

    没有操作系统的话，还存在进程吗？

    计算机可不可以没有操作系统？
6. js代码在运行过程中抛出异常，或运行了throw new Error()语句之后，会造成什么影响？影响范围是？
7. 什么是docker docker镜像 docker容器
8. 什么是静态资源？什么是动态资源？\
   前端静态资源为什么要单独部署到静态资源服务器？不这么做会导致什么后果？
9. <mark style="background-color:green;">什么样的数据适合放在全局store里？什么样的数据不适合放在全局store里？全局store的优点？</mark>\ <mark style="background-color:green;">结构化数据的好处？参考：配置文件、游戏存档</mark>\
   一般来讲，用户可与网页进行交互之前，我们需要对全局store的数据完成哪些操作？
10. package.json中：\
    版本号中^ \~ >=等符号的含义？\
    peerDependency的作用是什么？
11. react官方文档里推荐在复杂项目里使用useState吗？为什么？\
    <mark style="background-color:green;">useEffect(() => ... , \[]);内的代码有时候会运行两次，什么原因？</mark>\
    什么是react fiber？\
    Mobx与其他第三方库的组件（如ant-design）配合使用的时候应该注意什么呢？查阅mobx文档可知。\
    如何解决一个mobx store里定义的action太多的问题？
12. 阅读nextjs文档。

    概念理解：hydration, isomorphic app&#x20;

    在浏览器内，水合过程何时发生？react是如何判断是否应该进行水合操作的？

    nextjs服务从收到请求到返回html的过程？
13. nextjs中为什么要使用getLayout来实现页面中的公用layout？不用会有什么影响？\
    如果在nextjs项目的/src/pages目录下放了一些非page的组件，为什么在build过程中会报错呢？如何解决？
14. 列表渲染时的key起什么作用？不设置key的话会怎么样？要点在于虚拟dom节点的比较机制。\
    <mark style="background-color:green;">computed的比较典型的应用场景？</mark>[<mark style="background-color:green;">参考</mark>](computed-de-shi-yong.md)
15. 为什么不推荐使用px2rem自动把css中的px都转换成rem？带来的问题比解决的问题更多。

    为什么不推荐使用vw作为统一的长度单位？
16. PointerEvents MouseEvents TouchEvents应该使用哪个？\
    为什么在移动端网页上pointermove事件会被打断？如何解决？\
    Pointer events在桌面端和移动端的表现有哪些差异？\
    Pointer events的浏览器兼容性情况？
17. Circular dependency会引发哪些问题？如何规避？
18. 大量使用z-index，尤其是在多人项目中使用z-index会有什么影响？如何规避？
19. vue中的watcher是什么？一个vue组件有几个watcher？\
    vue是怎样进行依赖收集的？

<table data-full-width="true"><thead><tr><th width="135"></th><th>问题</th></tr></thead><tbody><tr><td></td><td>js代码在运行过程中抛出异常，或运行了throw new Error()语句之后，会造成什么影响？</td></tr><tr><td></td><td>为什么在移动端网页上pointermove事件会被打断？<br>Pointer events在桌面端和移动端的表现有哪些差异？</td></tr><tr><td></td><td>导致nodejs应用发生内存泄露的原因有哪些？如何排查？</td></tr><tr><td></td><td>RBAC</td></tr><tr><td>next</td><td>为什么nextjs在build过程中/src/pages目录下的组件文件会报错呢？如何解决？</td></tr><tr><td>mobx</td><td>Mobx与第三方组件配合使用的时候应该注意什么呢？查阅mobx文档可知。</td></tr><tr><td>mobx</td><td>如何解决一个mobx store里定义的action太多的问题？</td></tr><tr><td>react</td><td>什么是react fiber？</td></tr><tr><td>next</td><td>nextjs中为什么要使用getLayout来实现页面中的公用layout？不用会有什么影响？</td></tr><tr><td>mobx</td><td><mark style="background-color:green;">redux和mobx有哪些不同？</mark></td></tr><tr><td>react</td><td>列表渲染时的key起什么作用？不设置key的话会怎么样？要点在于虚拟dom节点的比较机制。</td></tr><tr><td></td><td><mark style="background-color:green;">computed的比较典型的应用场景？</mark></td></tr><tr><td></td><td>为什么记录选中某一item的时候要使用id而不是使用对象？</td></tr><tr><td><br></td><td>引用大体积的包时应该注意什么？</td></tr><tr><td><br></td><td>网页应用初始化的环节一般要完成哪些操作？</td></tr><tr><td><br></td><td><mark style="background-color:green;">结构化数据的好处？参考：配置文件、游戏存档</mark></td></tr><tr><td><br></td><td>为什么除非必要情况，不推荐在组件内使用dom api获取dom元素呢？</td></tr><tr><td><br></td><td><mark style="background-color:green;">什么样的数据适合放在store里？全局store的优点？</mark></td></tr><tr><td><br></td><td>react-lazy-load的原理？<a href="https://github.com/loktar00/react-lazy-load">https://github.com/loktar00/react-lazy-load</a></td></tr><tr><td><br></td><td>有ssr的项目和不涉及ssr的项目在store的使用上有什么需要注意的区别？</td></tr><tr><td>react</td><td><mark style="background-color:green;">useEffect内的代码为什么运行了两次？</mark></td></tr><tr><td><br></td><td><p><mark style="background-color:green;">express中间件是什么？</mark></p><p><mark style="background-color:green;">使用express的后端服务如何获取请求的cookie？</mark></p></td></tr><tr><td><br></td><td><p><mark style="background-color:green;">如何合并多条commits？</mark></p><p>什么是base commit？</p><p><mark style="background-color:green;">为什么运行git pull命令遇到冲突，解决冲突之后，再运行git rebase命令，又遇到了一模一样的冲突？</mark></p><p><mark style="background-color:green;">提交了太多条commit，之后进行rebase操作的时候遇到太多冲突，有没有办法规避？</mark></p></td></tr><tr><td>next</td><td><p>阅读nextjs文档。</p><p>概念理解：hydration, isomorphic app </p><p>在浏览器内，水合过程何时发生？react是如何判断是否应该进行水合操作的？</p><p>nextjs服务从收到请求到返回html的过程？</p></td></tr><tr><td><br></td><td>什么是docker docker镜像 docker容器</td></tr><tr><td><br></td><td>什么是domain？如何比较快地判断一个对象是不是domain？</td></tr><tr><td><br></td><td><p><mark style="background-color:green;">为什么99%的情况下可以不使用z-index？这些情况下用什么方法？</mark></p><p>swiper为何默认加了z-index: 1？</p></td></tr><tr><td><br></td><td><p>理解服务器、本地服务器、反向代理。</p><p>本地开发的时候访问的localhost是什么？webpack dev server、proxy table。</p></td></tr><tr><td><br></td><td>使用pixi.js输出的canvas画面为什么有明显的锯齿？</td></tr><tr><td><br></td><td><p>为什么不推荐使用px2rem自动把css中的px都转换成rem？带来的问题比解决的问题更多。</p><p>为什么不推荐使用vw作为统一的长度单位？</p></td></tr><tr><td><br></td><td>前端静态资源为什么要单独部署到静态资源服务器？不这么做会导致什么后果？</td></tr><tr><td><br></td><td>vue中的watcher是什么？一个vue组件有几个watcher？</td></tr><tr><td><br></td><td>vue是怎样进行依赖收集的？</td></tr><tr><td><br></td><td><p>DDD, business domain</p><p><a href="https://en.wikipedia.org/wiki/Domain-driven_design">https://en.wikipedia.org/wiki/Domain-driven_design</a></p><p><a href="http://www.javapractices.com/topic/TopicAction.do?Id=205">http://www.javapractices.com/topic/TopicAction.do?Id=205</a></p></td></tr><tr><td><br></td><td><p>进程 线程 堆内存 栈内存</p><p>没有操作系统的话，还存在进程吗？</p><p>计算机可不可以没有操作系统？</p></td></tr><tr><td><br></td><td>如何使function Dog继承function Animal。</td></tr></tbody></table>
