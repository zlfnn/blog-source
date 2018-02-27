---
title: list
date: 2018-02-07 09:16:20
tags:
---
### 动画代码
1. [动画](https://zlfnn.github.io/blog/1/run/1.html)
2. [动画](https://zlfnn.github.io/blog/1/run/2.html)
3. [动画](https://zlfnn.github.io/blog/1/run/3.html)
4. [动画](https://zlfnn.github.io/blog/1/run/4.html)
5. [动画](https://zlfnn.github.io/blog/1/run/5.html)
6. [动画](https://zlfnn.github.io/blog/1/run/6.html)
7. [动画](https://zlfnn.github.io/blog/1/run/7.html)
8. [动画](https://zlfnn.github.io/blog/1/run/8.html)
9. [动画](https://zlfnn.github.io/blog/1/run/9.html)
10. [动画](https://zlfnn.github.io/blog/1/run/10.html)
11. [动画](https://zlfnn.github.io/blog/1/run/11.html)
12. [动画](https://zlfnn.github.io/blog/1/run/12.html)
13. [动画](https://zlfnn.github.io/blog/1/run/13.html)
14. [动画](https://zlfnn.github.io/blog/1/run/14.html)
15. [动画](https://zlfnn.github.io/blog/1/run/15.html)
16. [动画](https://zlfnn.github.io/blog/1/run/16.html)
17. [动画](https://zlfnn.github.io/blog/1/run/17.html)
18. [动画](https://zlfnn.github.io/blog/1/run/18.html)
19. [动画](https://zlfnn.github.io/blog/1/run/18.html)
20. [动画](https://zlfnn.github.io/blog/1/run/18.html)

 
### h5
```
<header>用在页面的头部或者版块的头部</header>
<footer>用在页面的头部或者版块的底部</footer>
nav 导航
hgroup 标题组合
section 用来划分区域

<article>主体</article>
<aside>和主体相关的附属信息</aside>
<figure>
    <figcaption>妙味趣学</figcaption>  媒体元素
</figure>
<time datetime="2008-02-14">情人节</time>


<input type="text" list="valList" />
<datalist id="valList">
	<option value="javascript">javascript</option>
	<option value="html">html</option>
	<option value="css">css</option>
</datalist>


<details>
    <summary>妙味课堂</summary>
    <p>国内将知名的IT培训机构</p>
</details>

//对话
<dialog open>
  <dt>老师</dt>
  <dd>2+2 等于？</dd>
  <dt>学生</dt>
  <dd>4</dd>
  <dt>老师</dt>
  <dd>答对了！</dd>
</dialog>

<address>作者信息</address>
<mark>标记</mark>
进度条
<progress max="200" value="100">
	<span>76</span>%
</progress>

oDiv.dataset.miaovAll  //自定义属性
```

[h5兼容](https://www.caniuse.com/#index)

#### 拖拽

```
  ondragstart  方法  拖拽开始
  ondrag  开始与结束连续触发
  ondragend  拖拽结束

  ondragenter  拖拽进入
  ondragover  //enter和leave之间连续触发  //要想触发drop事件，就 必须在dragover当中阻止默认事件  ev.preventDefault();

<li draggable="true">a</li>
设置自定义属性
ev.dataTransfer.setData('name',this.index);
获取自定义属性
ev.dataTransfer.getData('name')

  ondragleave  拖拽离开

  ondrop 拖拽放开



  var fd = new FileReader();  上传文件
      
        fd.readAsDataURL( fs[i] );   
        
        fd.onload = function(){
          
          var oLi = document.createElement('li');
          var oImg = document.createElement('img');
          oImg.src = this.result;
          oLi.appendChild(oImg);
          oUl.appendChild(oLi);
          
        };
```
```
iframe

//如果我们要操作一个iframe里面的dom元素，首先要获取到iframe引入的页面的window
//oMyIframe.contentWindow -> 被iframe包含的页面的window对象
//alert(oMyIframe.contentWindow);  
oMyIframe.contentWindow.document.body.style.background = 'red';
//当本页面和包含页面不在同一个域名下的时候，这样操作就会有跨域操作安全限制问题。

    postMessage : 可以通过这个方法给另外一个窗口发送信息
  
    接收消息的窗口的window对象.postMessage();


    第一个参数：发送的数据
    第二个参数：接收数据的域名｛带上协议｝ 
    oMyIframe.contentWindow.postMessage('1', 'http://www.b.com');
/*
  message : 当窗口接收到通过postMessage发送过来的数据的时候触发
  */
  
  window.addEventListener('message', function(ev) {
    //alert('b.com下的页面接收到了内容了');
    
    //message事件的事件对象下保存了发送过来的内容
    //ev.data : 发送过来的数据
    //ev.origin
    
    //alert('我接收到了a.com页面发送过来的数据，内容是：' + ev.data);
    
    //alert(ev.origin);
    
    
    if (ev.data == '1') {
      document.body.style.background = 'red';
    }
    
  }, false);

//parent => window 如果当前页面是顶级，没有被其他页面所包含，那么parent就是当前页面的window对象，那么如果被包含了，则parent就是包含当前页面的父级页面的window对象
parent.document.body.style.background = 'green';

  window : 当前窗口 
  parent : 父级窗口
  top : 顶级窗口

//window.open 返回被打开窗口的window对象
newWindow = window.open('4.window.open.html', '_blank')
//window.opener : 通过window.open方法打开当前页面的窗口window
    window.opener.document.body.style.background = 'green';
```
```

/*
  在标准浏览器下，XMLHttpRequest对象已经是升级版本，支持了更多的特性，可以跨域了
  但是，如果想实现跨域请求，还需要后端的相关配合才可以
  
  XMLHttpRequest : 增加很多功能，他也不推荐使用onreadystatechange这个事件来监听，推荐使用onload
  
  XDomainRequest : IE如果想实现跨域请求，则需要使用另外一个对象去实现
  */
  var oBtn = document.getElementById('btn');
  
  oBtn.onclick = function() {
    
    /*var xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function() {
      if (xhr.readyState == 4) {
        if (xhr.status == 200) {
          alert(xhr.responseText);
        }
      }
    }
    xhr.open('get', 'http://www.b.com/ajax.php', true);
    xhr.send();*/
    
    var oXDomainRequest = new XDomainRequest();
    oXDomainRequest.onload = function() {
      alert(this.responseText);
    }
    oXDomainRequest.open('get', 'http://www.b.com/ajax.php', true);
    oXDomainRequest.send();
    
  }
```
