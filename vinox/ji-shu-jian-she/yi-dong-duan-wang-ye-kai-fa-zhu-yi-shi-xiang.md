# 移动端网页开发注意事项

移动端网页推荐使用rem作为单位。

设计图的宽度一般为750px。按照我们的换算方法，为width: 7.5rem。

示例：

font-size: 24px; => font-size: 0.24rem;

padding: 10px; => font-size: 0.1rem;



如何在手机浏览器/客户端测试包内访问本地开发环境的网页：

系统偏好设置→网络→找到本机的ip地址→手机浏览器内访问http://{本机ip}:{port}
