### 1. 自定义plugin 插件

```
jquery.extend(object);为扩展jquery类本身.为类添加新的方法
jquery.fn.extend(object);给jquery对象添加方法
```

```javascript
(function(jQuery){
    jQuery.extend({
        test: function(){
            alert("hello")
        }
    })
})(jQuery)
$.test()
```



### 2. 常见的plugin插件

#### 2.1 Validation

```html
<script type="text/javascript" src="<%=path %>/validate/jquery-1.6.2.min.js"></script>
<script type="text/javascript" src="<%=path %>/validate/jquery.validate.min.js"></script>
```

验证一个表格是否正确

```html
<form id="login">
    <input type="email" name="email" placeholder="邮箱" />
    <input type="password" name="password" placeholder="密码">
    <button type="submit" class="submit">提交</button>
</form>

<script>
    $().ready(function () {
        var validator = $("#login").validate({
            rules:{
                email:{
                    required:true,
                    email:true,

                }
            },
            debug:true
        });
        $('#login .submit')[0].addEventListener('click',function(){
            validator.resetForm();
        })
    });
</script>
```

