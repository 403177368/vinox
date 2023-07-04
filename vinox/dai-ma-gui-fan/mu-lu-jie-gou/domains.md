# /src/domains

## Folder Structure

* /domains[^1]
  * /domainTypes.ts
  * /post
    * /PostCard.tsx
    * /PostEditor.vue
    * /postService.ts
      * postInfo()
      * postList()
      * postCreate()
  * /product
    * /productService.ts
      * productInfo()
      * productList()
      * productCreate()
      * productDelete()
      * productStatusMap()

## Explanation

{% code fullWidth="true" %}
```yaml
/domains
  The directory contains domain related files, such as domain type class files and domain related components.
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
{% endcode %}



[^1]: The directory
