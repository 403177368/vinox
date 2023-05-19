# 小程序框架比较

<table data-full-width="true"><thead><tr><th>--</th><th>uni-app</th><th>taro</th><th>mpvue</th><th>wepy</th><th>megalo</th></tr></thead><tbody><tr><td>开发团队</td><td>DCloud 即数字天堂（北京）网络技术有限公司</td><td>京东凹凸实验室</td><td>美团</td><td>腾讯某前端</td><td>网易</td></tr><tr><td>官网地址</td><td><a href="https://uniapp.dcloud.io/README">https://uniapp.dcloud.io/README</a></td><td><a href="https://taro-docs.jd.com/taro/docs/README/index.html">https://taro-docs.jd.com/taro/docs/README/index.html</a></td><td><a href="http://mpvue.com/">http://mpvue.com/</a></td><td><a href="https://wepyjs.github.io/wepy-docs/">https://wepyjs.github.io/wepy-docs/</a></td><td><a href="https://megalojs.org/">https://megalojs.org/</a></td></tr><tr><td>模板中使用的主要标签</td><td>view</td><td>view与div均支持。</td><td>view</td><td>div</td><td>div</td></tr><tr><td>组件语法</td><td><p>类vue语法。</p><p>参考了mpvue</p></td><td>支持类vue语法。</td><td>类vue语法。</td><td>类vue语法。</td><td>类vue语法。</td></tr><tr><td>API封装</td><td><ol><li>Base64 字符串和ArrayBuffer 对象相互转换<br></li><li>路由跳转</li><li>网络请求</li><li>上传、下载</li><li>文件操作，例如图片选择</li><li>系统操作（不同平台支持情况不一）</li><li>拨打电话</li><li>获取系统信息。</li><li>网络状态</li><li>罗盘数据<br></li><li>剪贴板</li><li>缓存操作</li><li>定位</li><li>地图</li><li>键盘相关事件</li><li>loading事件</li><li>modal事件</li><li>设置title</li><li>下拉刷新</li><li>获取dom信息</li><li>canvas</li><li>登录</li><li>分享</li><li>消息推送</li></ol></td><td>Taro</td><td><br></td><td><br></td><td><br></td></tr><tr><td>开发者评价</td><td>社区活跃，用户较多</td><td><br></td><td><br></td><td>普遍评价不高。<a href="https://www.zhihu.com/question/266440872"><br>https://www.zhihu.com/question/266440872</a></td><td><br></td></tr><tr><td>Features</td><td><p>No virtual dom</p><p>No render function</p></td><td><p>Use virtual dom</p><p>No miniprogram components</p></td><td><br></td><td><br></td><td><br></td></tr><tr><td>缺点</td><td><p>No warning for absence of a required prop.</p><p>No type-validation for props.</p><p>'This' is not referenced to the parent instance when a prop function get invoked in the child component instance.</p><p>Prop value of a component is not reactive but a copy of the reactive value.</p></td><td><br></td><td><p>Call-expression in template not supported.</p><p>框架比较古老，代码仓库已数年未有更新。</p><p>模板中不支持复杂表达式。</p></td><td><br></td><td><br></td></tr><tr><td>小程序原生不支持</td><td><br></td><td></td><td></td><td></td><td></td></tr></tbody></table>

{% code fullWidth="true" %}
```
评价
  编译成原生app的功能并不实用，Weex基本是被废弃的框架。
  编译成网页应用的功能应被视为一个附加feature，即想将小程序页面顺便生成一个网页版本的时候使用，而不是相反。
  因小程序实际是浏览器环境下js语言的一个子集，实际与丰富的网页应用生态是割裂的，若一味迁就小程序开发，则无异于削足适履。
  
为什么不能使用小程序框架开发网页应用
  小程序语法是非标准化的，不遵循es规范。
  小程序无法直接使用npm packages，隔绝了js语言本身的生态，swiper iscroll等基于dom操作的优秀库都无法使用。
  受限于小程序语法的限制，很多js框架中习以为常的优秀特性都无法使用。
  “使用小程序语法开发网页应用、native应用”更多只是小程序框架开发团队的一种宣传，实际并无法实现传统网页应用的全部功能，所用demo只使用了可以实现的部分。
```
{% endcode %}

