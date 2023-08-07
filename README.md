# dz-copy
navigator.clipboard 仅支持通过 HTTPS 提供的页面。（根据需要自行更改源码）

## 安装
```
npm i dz
```
## 使用
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>剪切板</title>
</head>
<body>
  <button id="foo">COPY</button>
</body>
<script src="./index.js"></script>
<script>
  const copyBtn = document.getElementById('foo');
  copyBtn.onclick = function () {
    copyText('copy text', function () {
      // 成不成功无所谓，反正是结束了
      console.log('copy command was over')
    })
  }
</script>
</html>
```

## 注意

navigator.clipboard 仅支持通过 HTTPS 提供的页面。（根据需要自行更改源码）

为了防止滥用，只有当页面处于活动选项卡,并且用户手势内进行访问时，才允许剪贴板访问。

活动选项卡中的页面可以在不请求权限的情况下写入剪贴板，但从剪贴板中读取始终需要权限。

1.当页面处于活动选项卡问chatgpt吧，（ps: 浏览器devtool也属于是单独的选项卡）；

2.界定用户手势内进行访问： EventLoop机制下， 同步或异步（微任务）情况下。 宏任务后执行会超出界定。

https://developer.mozilla.org/zh-CN/docs/Web/API/Clipboard_API

替代

https://developer.mozilla.org/zh-CN/docs/Web/API/Document/execCommand
