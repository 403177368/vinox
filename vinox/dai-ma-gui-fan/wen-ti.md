# 问题

1. 以下哪种方式更好？\
   A const user = {} as User;\
   B const user: User = { id: '' };
2. “一件商品”的英文？\
   A good\
   B product
3. rem的方案：\
   A 直接使用rem。\
   B 使用px2rem。
4. 以下哪种写法更好？\
   A doSomething(name: string): void;\
   B doSomething: Function;
5. 以下哪种方式比较稳妥？\
   A 不使用可能有浏览器兼容性问题的、太新的api。\
   B 我也不知道有没有兼容性问题，用新奇的api显得厉害。
6. “创建日期”的英文：\
   A createTime\
   B createDate\
   C createdAt
7. id这一字段在前端用什么类型比较好？\
   A number\
   B string\
   C number | string\
   D any
8. 对于缩写你怎么看？\
   A: 只使用约定俗成的、比较常规的缩写。\
   B: 只是个名字而已，名字短点比较方便，快速完成需求。
9. 选项的数据类型设计方案？\
   A: tabMap: Record\<string, Tab>; activeTabId: string;\
   B: tabList: Tab\[]; activeTab: Tab;\
   C: tabList: Tab\[]; activeTabIndex: number;
10. nextjs项目里为什么不宜在代码里直接\`import store from '...'\`？&#x20;
