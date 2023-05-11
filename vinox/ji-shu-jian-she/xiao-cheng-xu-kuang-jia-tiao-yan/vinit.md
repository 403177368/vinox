# Vinit

<pre data-line-numbers><code>Vinit
  Features -- 自研小程序框架预计实现的功能及完成度：
    使用vue单文件组件。
      使用less.js将less代码转换为css代码。✅
      使用自研模板编译器将类vue模板编译为小程序模板：
        模板中可使用的标签：
          div、button、input、组件标签。
        Directives -- 模板中可使用的directives：
          v-if v-else v-elseif
          v-for
          v-show
          ref
          :class
            ObjectExpression
          :style
            ObjectExpression
          Event handling
            @click ✅
            Values
              Identifier
              ArrowFunctionExpression
              CallExpression
            Event modifiers
              stop
            Params
              $event
<strong>          CallExpression in vue template interpolation
</strong>          Slot

        使用babel编译转化vue单文件组件中的js部分。
          Module resolution
            支持使用绝对路径引用文件。 ✅
          Typescript syntax
            使用ts语法书写。 ✅
          支持process.env环境变量。使用babel-plugin-transform-inline-environment-variables实现。 ✅

        支持vue options：
          props
            type
            required
            Function-typed prop -- 支持函数类型的prop ✅
          data ✅
          computed ✅
          watch ✅
            deep
          mounted
          methods ✅
        Target platforms -- 源代码编译的目标平台：
          微信小程序 ✅
          支付宝小程序、QQ小程序、字节小程序、百度小程序代码。
        将各个小程序环境下常用的函数封装为统一的util层：
          使用babel-plugin-minify-dead-code-elimination在编译过程中将涉及非目标平台的代码删除。 ✅
          
observe data recursively
  generate a dep for every value

call proxy getter => return data value
call proxy setter => call data value setter => put dep into changedDependencyMap => schedule flush
call computed proxy getter => 
flush

微信小程序同样基于html css js实现，但语法经过微信方面定制，与h5相比，模板语法非常不同，禁用了部分常用的全局对象，大多常用的js库与组件无法直接引用。
目前市面上由各个公司开发，号称能由一套源代码编译部署成微信小程序、支付宝小程序、h5网页的框架，都存在诸多问题，例如功能不完全、框架出现bug维护者无人处理、框架不再有人维护等等。
并且这些框架的实现方案往往是让h5兼容小程序的语法，使得h5页面本身的功能反而受限。
</code></pre>
