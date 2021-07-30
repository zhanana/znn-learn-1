## Ajax在浏览器是通过XMLHttpRequest对象来实现数据传输的。

## XMLHttpReques对象进行http请求时必须通过open接受五个参数，分别为请求方法、请求链接、异步标识，账户与密码用以服务器端验证。

```javascript
    open(Method,URL,Asynchronous,UserName,password)
```

## 在成功初始化请求后，XMLHttpReques对象的setRequestHeader方法可以用来设置请求头。
```javascript
    setRequestHeader(key,value)
```
## 调用open()方法后，就可以通过调用send()方法按照open设定的参数将请求进行发送。

```javascript
    send(Data)
```

## 当open方法设定发送的方式为异步请求时，onreadystatechange事件监听器将自动XMLHttpReques对象的readyState属性改变时被触发。
```javascript
switch(readyState){
    case 1: break; //当open方法被成功调用,readyState为1
    case 2: break; //当send方法被调用，readyState属性被置为2
    case 3: break; //HTTP响应内容开始加载，readyState属性被置为3
    case 4: break; //HTTP响应内容结束加载，readyState属性被置为4
}
```
## 如果XMLHttpReques对象的readyState属性还没有变成4，abort可以终止请求。这个方法可以确保异步请求中的回调不被执行。

```javascript
    abort()
```
# ajax的简单实现
```javascript
    function ajax(url,method="GET",data=null,async=true){
        var XHR = XMLHttpRequest;
        XHR = new XMLHttpRequest()
        XHR.onreadystatechange = function(){
            if(XHR.readyState === 4)console.log(`响应状态:${XHR.status}`,"FINISH")
        }
        XHR.open(method,url,async)
        XHR.send(data)
    }
        ajax("https://www.baidu.com");
        ajax("https://www.baidu.com","POST","A=1&B=2");
```