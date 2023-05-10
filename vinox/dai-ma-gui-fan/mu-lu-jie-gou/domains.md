# /src/domains

```yaml
What is domain?
  Posts related:
    https://docs.github.com/en/graphql/reference/objects
    https://en.wikipedia.org/wiki/Domain-driven_design
    Package by feature, not layer: http://www.javapractices.com/topic/TopicAction.do?Id=205
  简单的判断方法：一个domainObject必有id字段，对应数据库的一张数据表中的某条记录。如果一个对象没有id，那么它大概率是附属于某一domainObject下的一个属性值。

/domains
  The directory containing domain related files, such as domain type class files and domain related components.
  强化domain概念，新需求均围绕domains文件夹展开。
  /post
    PostEditor.vue
    PostCard.vue
    postService.ts
  /product
    productService.ts
    service文件：
      Introduction
        Service paradigm is learnt from Java ecosystem.
        A service is a collection of methods to CRUD specified domain objects.
      service文件应该以 `${domainName}Service.js` 方式命名。
      domainName涉及业务逻辑中对某一概念的命名，应该慎重考虑之后再命名。
      目前构建项目时脚本会读取分析service文件中定义的函数名并校验，如果遇到非法函数名将抛出异常。
      Examples:
        productService.ts
        productList()
        productInfo()
        productCreate()
```

| 英文                   | 中文     | 备注                                                                                                                                        |
| -------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| business             | 商家     | A business is an organization which produces and sells goods or which provides a service.                                                 |
| organization         | 机构     |                                                                                                                                           |
| product              | 商品     | <p>推荐使用product。</p><p>goods是集合名词，没有单数形式。</p>                                                                                              |
| order                | 订单     |                                                                                                                                           |
| receipt              | 发票     | [https://zhuanlan.zhihu.com/p/135483316](https://zhuanlan.zhihu.com/p/135483316)                                                          |
| message              | 一条日志   | log是集合名词。log中的一条日志称为message。                                                                                                              |
| consultationQuestion | 快速咨询问题 |                                                                                                                                           |
| post                 | 文章     | Post is a piece of writing, image, or other item of content published online, typically on a blog or social media website or application. |
