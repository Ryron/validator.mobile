# mbvalidator
移动端验证框架
## 访问
```
npm install 

npm run dev

http://localhost:8080/examples/xxx.html
```
## 使用
```
<form id="testForm">
	 <input type="text"  placeholder="" value="" data-rules="required;" data-descriptions="用户名">
</form>
<!-- 引入js -->
<script src='../static/zepto/zepto.min.js'></script>
<script src="../assets/validator.min.js?"></script>
```

引入zepto和validator，验证内容必须包含在`form`标签内容。

```
var form = $('#testForm').mbValidate({
  prompt: function (msg) {
    $.alert(msg);
  }
}, function () {
  console.log('success');
}, function () {
  console.log('error');
});
```

`$('#formId').mbValidate(options, success, error)`

validate方法接受3个参数options、success、error。

| 参数        |      说明      | 备注  |
| ------------- |:-------------:| -----|
| options | 配置，prompt 弹窗方法 |    |
| success | 验证成功          |    |
| error | 验证失败 | 默认给验证失败的表单添加class color-error |