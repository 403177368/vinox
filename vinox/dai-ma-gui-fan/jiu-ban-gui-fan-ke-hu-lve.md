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
```
{% endcode %}
