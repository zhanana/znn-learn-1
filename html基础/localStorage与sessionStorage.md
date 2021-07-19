### localStorage 与 sessionStorage 是 HTML5 提供的对于 web 存储的解决方案

## 相同点

- 都与 http 无关，当发起 http 请求时不会与 cookie 一样自动携带。
- 都是以键值对 key-value 形式存在，常用的 API 也相同。
- 存储类型都是 string 类型，当进行存储时，会调用 toString()方法 转为 string 类型
- 对于每个容量是有限的，每个浏览器都不一样，一般在 5M 左右

## 不同点

- localStorage 用于持久化的本地存储，除非主动删除数据，否则数据永远不过期。

* sessionStorage 会在用户关闭浏览器后，即会话结束后，数据失效，session Storage 与 服务端 session 无关。

## 常用操作

- 存储数据

```javascript
localStorage.setItem("key", "value");
sessionStorage.setItem("key", "value");
//进行存储的时候会调用toString()方法
```

- 读取数据

```javascript
localStorage.getItem("key");
sessionStorage.getItem("key");
```

- 删除数据

```javascript
localStorage.removeItem("key");
sessionStorage.removeItem("key");
```

- 清空数据

```javascript
localStorage.clear();
sessionStorage.clear();
```
