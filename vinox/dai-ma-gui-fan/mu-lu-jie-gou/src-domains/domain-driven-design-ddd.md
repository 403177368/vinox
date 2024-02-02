# Domain Driven Design / DDD

**DDD is a design pattern for business system.**

## Posts about DDD

{% embed url="https://en.wikipedia.org/wiki/Domain-driven_design" %}

{% embed url="https://docs.github.com/en/graphql/reference/objects" %}

{% embed url="http://www.javapractices.com/topic/TopicAction.do?Id=205" %}

## How to Name a Domain Object?

* A **domain object name** must be **singular form of countable noun**.
* A **domain object** must has \`id\` field.
* A domain object class usually has a database table to store its domain objects.

### Examples

<table data-full-width="true"><thead><tr><th width="251">英文</th><th width="157.33333333333331">中文</th><th>备注</th></tr></thead><tbody><tr><td>business</td><td>商家</td><td>A business is an organization which produces and sells goods or which provides a service.</td></tr><tr><td>organization</td><td>机构</td><td></td></tr><tr><td>product</td><td>商品</td><td><p>推荐使用product。</p><p>goods是集合名词，没有单数形式。</p></td></tr><tr><td>order</td><td>订单</td><td></td></tr><tr><td>receipt</td><td>发票</td><td><a href="https://zhuanlan.zhihu.com/p/135483316">https://zhuanlan.zhihu.com/p/135483316</a></td></tr><tr><td>message</td><td>一条日志</td><td>log是集合名词。log中的一条日志称为message。</td></tr><tr><td>consultationQuestion</td><td>快速咨询问题</td><td></td></tr><tr><td>post</td><td>文章</td><td>Post is a piece of writing, image, or other item of content published online, typically on a blog or social media website or application.</td></tr></tbody></table>

## What is domain?

