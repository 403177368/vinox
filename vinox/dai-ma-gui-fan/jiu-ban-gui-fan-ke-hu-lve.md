# 旧版规范（可忽略）

{% code fullWidth="true" %}
```
说明：
  公用组件、公用方法等等，应该经由团队讨论、方案成熟之后再投入使用。
  项目中使用了自定义的eslint-plugin-dictator插件，插件中自定义了一些eslint规则，对代码进行校验。（已中止）
    
    Typescript:
      For avoiding dependency cycle problem, all the commonly used types and interfaces are put in a single file.
      目的：使用Typescript进行统一的类型规范，并在编译时就发现问题。types和interfaces应该是通用的。
      Typescript无法校验vue模板中的变量类型的解决方案：
        使用tsx和vue-tsx-support，方案并不成熟，还有一些问题待解决。
      Type 'any' must not be used if not necessary.
      非必要不使用any。[重要]
    
    第三方组件：
      如果可能的话，中后台项目中都推荐都使用element-ui框架的el-table组件，已引入，使用方法参考商家后台/Test路由下的内容。该table组件的用法比view-design的表格组件更为简洁。
      中后台每个页面的搜索条件表单区域，如果没有设计图，推荐使用<Form inline :label-width="xxx"></Form>。这样既不用写额外的样式，又能有不错的响应式功能。
      中台已经引入ag-grid库，未来的一些涉及统计数据的相关界面需求，如果有单表超过千行的表格，推荐使用这个库。
      
命名：
  静态资源文件，如png、svg、mp3等文件，其命名允许使用PascalCase、camelCase、kebab-case、snake_case，但禁止一个类名中出现各种case混用的情况，如whatever_Case。
  “跳转”相关方法名中禁止出现“jump”字样。推荐使用toBlablabla方式命名。
  非必要情况下，禁止在css中自定义全局类名。除非产出一套成熟的通用全局类名。
  如果在变量命名中出现list或map等字样，禁止出现名字与数据类型不对应的情况。
  eventHandler的命名，推荐使用以下方式：onConfirmButtonClicked等。
    onConfirmButtonClicked
    onCloseButtonClicked
    event naming conventions：
      The object action framework：
        https://segment.com/academy/collecting-data/naming-conventions-for-clean-data/
        https://mixedanalytics.com/blog/event-tracking-naming-strategy-for-google-analytics/
      Other examples of event naming：
        https://flutter.dev/docs/cookbook/forms/text-field-changes
        https://developer.android.com/reference/androidx/recyclerview/widget/RecyclerView.OnScrollListener
        https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/menus/onClicked

组件：
  组件名：
    CommonHeader.vue CommonHeader.tsx
    The name of a component file should be pascal-cased and globally unique. Avoid using over-simple names.
    自定义单文件组件的命名均应使用PascalCase。尽量保证全局唯一，避免使用过于简单的命名，如Info、Details等，而应使用BusinessDetails、ProductDetails等。
  组件文件模板的根标签须设置一个跟组件文件同名的PascalCase的类名。
  若某一组件需要引用只有它自身用到的资源文件，如图片、音频、css文件，则需创建一个文件夹，把这些文件放到文件夹内。如MyComponent.vue变为MyComponent/index.vue，MyComponent/some-img.png等等。

  模板：
    页面中使用的大图片，必须使用tinypng进行压缩。
    
  css：
    组件文件的css内容必须用根标签的className包裹，如.BusinessDetails { ...... }。
    css中使用类名时，应严格对应模板中类名的嵌套关系，禁止类名落单出现。
    css类名允许使用PascalCase、camelCase、kebab-case、underscore_case，但禁止一个类名中出现各种case混用的情况，如whatever_Case。
    非必要情况下，css中应尽量使用className，而不是id。
    非必要情况下，禁止在css中直接使用div、img、ul、li、span等等原生html标签名，以及 * 。（为了避免滥用）
    非必要情况下，禁止在css中使用:first-child :last-child :nth-child等等伪类。（为了避免滥用）
    非必要情况下，禁止使用背景图片代替img标签。
    非必要情况下，禁止在css代码中使用@import。
    禁止wrap字样的类名（错误用法），可使用wrapper字样。

  js：
    引用src目录下的文件时，使用以'@/'开头的如下路径，例如'@/assets/'，'@/components/'等等。
    商家后台项目，在组件的beforeRouteEnter生命周期钩子函数中设置breadcrumb导航及其他route.meta中的属性。
    推荐使用const self = this，不推荐使用const that = this，禁止使用const _this = this。
    The view-design package in not recommended any more.
    使用view-design框架中的Table组件时，禁止使用render函数，而应该使用slot。
    中后台确认弹窗使用全局的await this.$confirm()方法。
    Router navigation:
      vue-router路由跳转使用this.𝑟𝑜𝑢𝑡𝑒𝑟.𝑝𝑢𝑠ℎ(𝑛𝑎𝑚𝑒:′𝑆𝑜𝑚𝑒𝑁𝑎𝑚𝑒′)或𝑡ℎ𝑖𝑠.
      router.replace()方法，禁止使用this.$router.push('/some-path')这种调用方式。
    使用<router-link :to="{ path: '/some-path' }">，原因同上。
    提交代码时禁止出现console，如必须，可将console所在行注释掉，或标注eslint-disable。
    禁止使用一些比较新的、可能有浏览器兼容性问题的js原生api，例如String.prototype.replaceAll、Array.prototype.flatMap、Set、Map等等。
    使用String.prototype.trim方法去除字符串两端的空格，不要使用/^\s+|\s+$/g之类的正则去实现这一功能。
    非必要情况下，自定义的组件里禁止使用this.𝑒𝑚𝑖𝑡，而应该使用𝑝𝑟𝑜𝑝𝑠:𝑠𝑜𝑚𝑒𝐹𝑢𝑛𝑐𝑡𝑖𝑜𝑛𝑁𝑎𝑚𝑒:𝑟𝑒𝑞𝑢𝑖𝑟𝑒𝑑:𝑡𝑟𝑢𝑒，把方法从上层传入组件内使用，规避emit这种过于灵活的使用。
```
{% endcode %}
